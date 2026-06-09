# EapQueryAggregatedEventConditionNextChild

- ea: `0x180009ef0`
- end: `0x180009fe6`
- name: `EapQueryAggregatedEventConditionNextChild`
- size: `246`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `reparse_path, authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x180009940`
- `0x180009ef0`

## import_xrefs

- `ntdll!ZwClose` at `0x180009fc9`
- `ntdll!ZwClose` at `0x180009fc9`
- `ntdll!ZwOpenKey` at `0x180009fa5`
- `ntdll!ZwOpenKey` at `0x180009fa5`

## pseudocode

```c
__int64 __fastcall EapQueryAggregatedEventConditionNextChild(__int64 a1, void *a2, unsigned __int16 a3, void **a4)
{
  __int64 *v4; // rsi
  int v7; // eax
  NTSTATUS v8; // ebx
  __int64 v9; // rcx
  __int128 v11; // [rsp+20h] [rbp-40h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+30h] [rbp-30h] BYREF
  void *KeyHandle; // [rsp+80h] [rbp+20h] BYREF

  v4 = (__int64 *)(a1 + 16);
  KeyHandle = 0;
  memset(&ObjectAttributes, 0, 44);
  v11 = 0;
  v7 = EapEnumerateKey(a2, a3);
  v8 = v7;
  if ( v7 == -2147483622 )
  {
    *a4 = 0;
    v8 = 0;
  }
  else if ( v7 >= 0 )
  {
    v9 = *v4;
    if ( *(_DWORD *)(*v4 + 12) <= 0xFFFFu )
    {
      *((_QWORD *)&v11 + 1) = v9 + 16;
      LOWORD(v11) = *(_WORD *)(v9 + 12);
      WORD1(v11) = v11;
      ObjectAttributes.ObjectName = (PUNICODE_STRING)&v11;
      ObjectAttributes.Length = 48;
      ObjectAttributes.RootDirectory = a2;
      ObjectAttributes.Attributes = 64;
      *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
      v8 = ZwOpenKey(&KeyHandle, 0xF003Fu, &ObjectAttributes);
      if ( v8 >= 0 )
      {
        *a4 = KeyHandle;
        KeyHandle = 0;
      }
    }
    else
    {
      v8 = -2147483643;
    }
  }
  if ( KeyHandle )
    ZwClose(KeyHandle);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x180009ef0  mov     [rsp-18h+arg_8], rbx
0x180009ef5  mov     [rsp-18h+arg_10], rsi
0x180009efa  push    rbp
0x180009efb  push    rdi
0x180009efc  push    r14
0x180009efe  mov     rbp, rsp
0x180009f01  sub     rsp, 60h
0x180009f05  xorps   xmm0, xmm0
0x180009f08  lea     rsi, [rcx+10h]
0x180009f0c  mov     r14, rdx
0x180009f0f  xor     eax, eax
0x180009f11  movzx   edx, r8w; Index
0x180009f15  mov     rcx, r14; KeyHandle
0x180009f18  movups  xmmword ptr [rbp+ObjectAttributes.ObjectName], xmm0
0x180009f1c  mov     r8, rsi
0x180009f1f  mov     [rbp+KeyHandle], rax
0x180009f23  movups  xmmword ptr [rbp+ObjectAttributes+1Ch], xmm0
0x180009f27  mov     rdi, r9
0x180009f2a  movups  xmmword ptr [rbp+ObjectAttributes.Length], xmm0
0x180009f2e  movups  [rbp+var_40], xmm0
0x180009f32  call    EapEnumerateKey
0x180009f37  mov     ebx, eax
0x180009f39  cmp     eax, 8000001Ah
0x180009f3e  jnz     short loc_180009F4B
0x180009f40  mov     qword ptr [rdi], 0
0x180009f47  xor     ebx, ebx
0x180009f49  jmp     short loc_180009FC0
0x180009f4b  test    eax, eax
0x180009f4d  js      short loc_180009FC0
0x180009f4f  mov     rcx, [rsi]
0x180009f52  cmp     dword ptr [rcx+0Ch], 0FFFFh
0x180009f59  jbe     short loc_180009F62
0x180009f5b  mov     ebx, 80000005h
0x180009f60  jmp     short loc_180009FC0
0x180009f62  lea     rax, [rcx+10h]
0x180009f66  xorps   xmm0, xmm0
0x180009f69  mov     qword ptr [rbp+var_40+8], rax
0x180009f6d  lea     r8, [rbp+ObjectAttributes]; ObjectAttributes
0x180009f71  movzx   eax, word ptr [rcx+0Ch]
0x180009f75  mov     edx, 0F003Fh; DesiredAccess
0x180009f7a  mov     word ptr [rbp+var_40], ax
0x180009f7e  lea     rcx, [rbp+KeyHandle]; KeyHandle
0x180009f82  mov     word ptr [rbp+var_40+2], ax
0x180009f86  lea     rax, [rbp+var_40]
0x180009f8a  mov     [rbp+ObjectAttributes.ObjectName], rax
0x180009f8e  mov     [rbp+ObjectAttributes.Length], 30h ; '0'
0x180009f95  mov     [rbp+ObjectAttributes.RootDirectory], r14
0x180009f99  mov     [rbp+ObjectAttributes.Attributes], 40h ; '@'
0x180009fa0  movdqu  xmmword ptr [rbp+ObjectAttributes.SecurityDescriptor], xmm0
0x180009fa5  call    cs:__imp_ZwOpenKey
0x180009fab  mov     ebx, eax
0x180009fad  test    eax, eax
0x180009faf  js      short loc_180009FC0
0x180009fb1  mov     rax, [rbp+KeyHandle]
0x180009fb5  mov     [rdi], rax
0x180009fb8  mov     [rbp+KeyHandle], 0
0x180009fc0  mov     rcx, [rbp+KeyHandle]; Handle
0x180009fc4  test    rcx, rcx
0x180009fc7  jz      short loc_180009FCF
0x180009fc9  call    cs:__imp_ZwClose
0x180009fcf  lea     r11, [rsp+60h+var_s0]
0x180009fd4  mov     eax, ebx
0x180009fd6  mov     rbx, [r11+28h]
0x180009fda  mov     rsi, [r11+30h]
0x180009fde  mov     rsp, r11
0x180009fe1  pop     r14
0x180009fe3  pop     rdi
0x180009fe4  pop     rbp
0x180009fe5  retn
```
