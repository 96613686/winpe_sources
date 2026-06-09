# PiRegStateOpenClassKey

- ea: `0x1400253a8`
- end: `0x140025533`
- name: `PiRegStateOpenClassKey`
- size: `395`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x140025724`
- `0x140025890`

## callees

- `0x140013b00`
- `0x1400253a8`
- `0x140025b0c`
- `0x140025be0`

## import_xrefs

- `ntoskrnl!ZwClose` at `0x1400254e9`
- `ntoskrnl!ZwClose` at `0x1400254e9`
- `ntoskrnl!_snwprintf` at `0x140025489`
- `ntoskrnl!_snwprintf` at `0x140025489`

## string_xrefs

- `0x140025402`: `\Registry\Machine\System\CurrentControlSet\Control\Class`

## pseudocode

```c
NTSTATUS __fastcall PiRegStateOpenClassKey(unsigned int *a1, __int64 a2, int a3, ULONG *a4, _QWORD *a5)
{
  NTSTATUS result; // eax
  __int64 v9; // r8
  ULONG v10; // r9d
  HANDLE v11; // rbx
  NTSTATUS v12; // eax
  ULONG v13; // esi
  int v14; // edi
  ULONG v15; // [rsp+70h] [rbp-61h] BYREF
  HANDLE Handle; // [rsp+78h] [rbp-59h] BYREF
  void *v17[2]; // [rsp+80h] [rbp-51h] BYREF
  wchar_t Dest[40]; // [rsp+90h] [rbp-41h] BYREF

  Handle = 0;
  v17[0] = 0;
  v15 = 0;
  *a5 = 0;
  if ( a4 )
    *a4 = 0;
  result = CmRegUtilOpenExistingWstrKey(
             0,
             L"\\Registry\\Machine\\System\\CurrentControlSet\\Control\\Class",
             131097,
             &Handle);
  if ( result >= 0 )
  {
    _snwprintf(
      Dest,
      0x27u,
      L"{%08X-%04X-%04X-%02X%02X-%02X%02X%02X%02X%02X%02X}",
      *a1,
      *((unsigned __int16 *)a1 + 2),
      *((unsigned __int16 *)a1 + 3),
      *((unsigned __int8 *)a1 + 8),
      *((unsigned __int8 *)a1 + 9),
      *((unsigned __int8 *)a1 + 10),
      *((unsigned __int8 *)a1 + 11),
      *((unsigned __int8 *)a1 + 12),
      *((unsigned __int8 *)a1 + 13),
      *((unsigned __int8 *)a1 + 14),
      *((unsigned __int8 *)a1 + 15));
    v11 = Handle;
    Dest[38] = 0;
    if ( a3 )
    {
      v12 = CmRegUtilCreateWstrKey((__int64)Handle, Dest, v9, v10, 0, &v15, v17);
      v13 = v15;
    }
    else
    {
      v12 = CmRegUtilOpenExistingWstrKey((__int64)Handle, Dest, 983103, v17);
      v13 = 2;
    }
    v14 = v12;
    ZwClose(v11);
    if ( v14 >= 0 )
    {
      *a5 = v17[0];
      if ( a4 )
        *a4 = v13;
    }
    return v14;
  }
  return result;
}

```

## disassembly

```asm
0x1400253a8  mov     [rsp-8+arg_8], rbx
0x1400253ad  push    rbp
0x1400253ae  push    rsi
0x1400253af  push    rdi
0x1400253b0  push    r12
0x1400253b2  push    r13
0x1400253b4  push    r14
0x1400253b6  push    r15
0x1400253b8  lea     rbp, [rsp-1Fh]
0x1400253bd  sub     rsp, 0F0h
0x1400253c4  mov     rax, cs:__security_cookie
0x1400253cb  xor     rax, rsp
0x1400253ce  mov     [rbp+4Fh+var_40], rax
0x1400253d2  mov     r12, [rbp+4Fh+arg_20]
0x1400253d6  xor     ebx, ebx
0x1400253d8  mov     [rbp+4Fh+Handle], rbx
0x1400253dc  mov     r14, r9
0x1400253df  mov     [rbp+4Fh+var_A0], rbx
0x1400253e3  mov     r13d, r8d
0x1400253e6  mov     [rbp+4Fh+var_B0], ebx
0x1400253e9  mov     r15, rcx
0x1400253ec  mov     [r12], rbx
0x1400253f0  test    r9, r9
0x1400253f3  jz      short loc_1400253F8
0x1400253f5  mov     [r9], ebx
0x1400253f8  lea     r9, [rbp+4Fh+Handle]
0x1400253fc  mov     r8d, 20019h
0x140025402  lea     rdx, aRegistryMachin; "\\Registry\\Machine\\System\\CurrentCon"...
0x140025409  xor     ecx, ecx
0x14002540b  call    CmRegUtilOpenExistingWstrKey
0x140025410  test    eax, eax
0x140025412  js      loc_14002550B
0x140025418  movzx   ecx, byte ptr [r15+0Eh]
0x14002541d  movzx   edx, byte ptr [r15+0Dh]
0x140025422  movzx   r8d, byte ptr [r15+0Ch]
0x140025427  movzx   r9d, byte ptr [r15+0Bh]
0x14002542c  movzx   eax, byte ptr [r15+0Fh]
0x140025431  movzx   r10d, byte ptr [r15+0Ah]
0x140025436  movzx   r11d, byte ptr [r15+9]
0x14002543b  movzx   ebx, byte ptr [r15+8]
0x140025440  movzx   edi, word ptr [r15+6]
0x140025445  movzx   esi, word ptr [r15+4]
0x14002544a  mov     [rsp+120h+var_B8], eax
0x14002544e  mov     [rsp+120h+var_C0], ecx
0x140025452  lea     rcx, [rbp+4Fh+Dest]; Dest
0x140025456  mov     [rsp+120h+var_C8], edx
0x14002545a  mov     edx, 27h ; '''; Count
0x14002545f  mov     [rsp+120h+var_D0], r8d
0x140025464  lea     r8, a08x04x04x02x02; "{%08X-%04X-%04X-%02X%02X-%02X%02X%02X%0"...
0x14002546b  mov     [rsp+120h+var_D8], r9d
0x140025470  mov     r9d, [r15]
0x140025473  mov     [rsp+120h+var_E0], r10d
0x140025478  mov     [rsp+120h+var_E8], r11d
0x14002547d  mov     dword ptr [rsp+120h+var_F0], ebx
0x140025481  mov     dword ptr [rsp+120h+var_F8], edi
0x140025485  mov     dword ptr [rsp+120h+var_100], esi
0x140025489  call    cs:__imp__snwprintf
0x140025490  nop     dword ptr [rax+rax+00h]
0x140025495  mov     rbx, [rbp+4Fh+Handle]
0x140025499  lea     rdx, [rbp+4Fh+Dest]
0x14002549d  xor     eax, eax
0x14002549f  mov     rcx, rbx
0x1400254a2  mov     [rbp+4Fh+var_44], ax
0x1400254a6  test    r13d, r13d
0x1400254a9  jz      short loc_1400254D0
0x1400254ab  lea     rax, [rbp+4Fh+var_A0]
0x1400254af  mov     [rsp+120h+var_F0], rax
0x1400254b4  lea     rax, [rbp+4Fh+var_B0]
0x1400254b8  mov     [rsp+120h+var_F8], rax
0x1400254bd  mov     [rsp+120h+var_100], 0
0x1400254c6  call    CmRegUtilCreateWstrKey
0x1400254cb  mov     esi, [rbp+4Fh+var_B0]
0x1400254ce  jmp     short loc_1400254E4
0x1400254d0  lea     r9, [rbp+4Fh+var_A0]
0x1400254d4  mov     r8d, 0F003Fh
0x1400254da  call    CmRegUtilOpenExistingWstrKey
0x1400254df  mov     esi, 2
0x1400254e4  mov     rcx, rbx; Handle
0x1400254e7  mov     edi, eax
0x1400254e9  call    cs:__imp_ZwClose
0x1400254f0  nop     dword ptr [rax+rax+00h]
0x1400254f5  test    edi, edi
0x1400254f7  js      short loc_140025509
0x1400254f9  mov     rax, [rbp+4Fh+var_A0]
0x1400254fd  mov     [r12], rax
0x140025501  test    r14, r14
0x140025504  jz      short loc_140025509
0x140025506  mov     [r14], esi
0x140025509  mov     eax, edi
0x14002550b  mov     rcx, [rbp+4Fh+var_40]
0x14002550f  xor     rcx, rsp; StackCookie
0x140025512  call    __security_check_cookie
0x140025517  mov     rbx, [rsp+120h+arg_8]
0x14002551f  add     rsp, 0F0h
0x140025526  pop     r15
0x140025528  pop     r14
0x14002552a  pop     r13
0x14002552c  pop     r12
0x14002552e  pop     rdi
0x14002552f  pop     rsi
0x140025530  pop     rbp
0x140025531  retn
```
