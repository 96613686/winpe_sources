# BaseRegDeleteKeyExInternal

- ea: `0x180026560`
- end: `0x1800266d4`
- name: `BaseRegDeleteKeyExInternal`
- size: `372`
- prototype: `__int64 __fastcall(HANDLE KeyHandle, PCUNICODE_STRING Source)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, loader_planting`

## callers

- `0x180026430`

## callees

- `0x180026560`
- `0x1800266dc`
- `0x180026e34`
- `0x1800413f4`
- `0x18006dd70`

## import_xrefs

- `ntdll!NtClose` at `0x18002661c`
- `ntdll!NtClose` at `0x18002661c`
- `ntdll!NtDeleteKey` at `0x18002660a`
- `ntdll!NtDeleteKey` at `0x18002660a`
- `ntdll!RtlNtStatusToDosError` at `0x18002662e`
- `ntdll!RtlNtStatusToDosError` at `0x18002662e`
- `KERNELBASE!RegKrnGetTermsrvRegistryExtensionFlags` at `0x180026651`
- `KERNELBASE!RegKrnGetTermsrvRegistryExtensionFlags` at `0x180026651`
- `KERNEL32!TermsrvDeleteKey` at `0x1800266b9`
- `KERNEL32!TermsrvDeleteKey` at `0x1800266b9`

## pseudocode

```c
ULONG __fastcall BaseRegDeleteKeyExInternal(HANDLE KeyHandle, UNICODE_STRING *Source)
{
  HANDLE v3; // rdi
  unsigned int Length; // edx
  PWSTR Buffer; // rcx
  UNICODE_STRING v6; // xmm6
  int v7; // edi
  int v9; // r9d
  int v10; // eax
  void *v11; // [rsp+20h] [rbp-50h]
  int v12[4]; // [rsp+30h] [rbp-40h] BYREF
  UNICODE_STRING *v13; // [rsp+40h] [rbp-30h]
  int v14; // [rsp+48h] [rbp-28h]
  int v15; // [rsp+4Ch] [rbp-24h]
  __int128 v16; // [rsp+50h] [rbp-20h]
  HANDLE v17; // [rsp+90h] [rbp+20h] BYREF
  HANDLE KeyHandlea; // [rsp+98h] [rbp+28h] BYREF

  v17 = KeyHandle;
  v12[1] = 0;
  v15 = 0;
  v3 = KeyHandle;
  KeyHandlea = 0;
  if ( Source )
  {
    Length = Source->Length;
    if ( Length >= 2 )
    {
      Buffer = Source->Buffer;
      if ( Buffer )
      {
        if ( (Length & 1) == 0 && !Buffer[((unsigned __int64)Length >> 1) - 1] )
        {
          v6 = *Source;
          Source->Length = Length - 2;
          if ( ((unsigned __int8)v3 & 2) != 0
            || (RegKrnGetTermsrvRegistryExtensionFlags() & 2) != 0
            && (v10 = ExtractClassKey(&v17, Source), v3 = v17, v10) )
          {
            v7 = BaseRegOpenClassKey(v3, Source, (__int64)&KeyHandlea);
            if ( v7 < 0 )
            {
LABEL_12:
              *Source = v6;
              return RtlNtStatusToDosError(v7);
            }
          }
          else
          {
            v12[0] = 48;
            v12[2] = (int)v3;
            v12[3] = HIDWORD(v17);
            v16 = 0;
            v14 = 64;
            v13 = Source;
            v7 = Wow64NtOpenKey((int)&KeyHandlea, 0x10000, (int)v12, v9, v11);
          }
          if ( (unsigned __int8)IsTermsrvDeleteKeyPresent() )
            TermsrvDeleteKey(KeyHandlea);
          if ( v7 >= 0 )
          {
            v7 = NtDeleteKey(KeyHandlea);
            NtClose(KeyHandlea);
          }
          goto LABEL_12;
        }
      }
    }
  }
  return 87;
}

```

## disassembly

```asm
0x180026560  mov     [rsp-18h+arg_10], rbx
0x180026565  mov     [rsp-18h+arg_0], rcx
0x18002656a  push    rbp
0x18002656b  push    rdi
0x18002656c  push    r14
0x18002656e  mov     rbp, rsp
0x180026571  sub     rsp, 70h
0x180026575  xor     r14d, r14d
0x180026578  movaps  [rsp+70h+var_10], xmm6
0x18002657d  mov     [rbp+var_3C], r14d
0x180026581  mov     rbx, rdx
0x180026584  mov     [rbp+var_24], r14d
0x180026588  mov     rdi, rcx
0x18002658b  mov     [rbp+KeyHandle], r14
0x18002658f  test    rdx, rdx
0x180026592  jz      loc_1800266CA
0x180026598  movzx   edx, word ptr [rdx]
0x18002659b  cmp     edx, 2
0x18002659e  jb      loc_1800266CA
0x1800265a4  mov     rcx, [rbx+8]
0x1800265a8  test    rcx, rcx
0x1800265ab  jz      loc_1800266CA
0x1800265b1  test    dl, 1
0x1800265b4  jnz     loc_1800266CA
0x1800265ba  mov     eax, edx
0x1800265bc  shr     rax, 1
0x1800265bf  cmp     [rcx+rax*2-2], r14w
0x1800265c5  jnz     loc_1800266CA
0x1800265cb  movups  xmm6, xmmword ptr [rbx]
0x1800265ce  sub     dx, 2
0x1800265d2  mov     [rbx], dx
0x1800265d5  test    dil, 2
0x1800265d9  jz      short loc_180026651
0x1800265db  lea     rax, [rbp+KeyHandle]
0x1800265df  mov     rdx, rbx; Source
0x1800265e2  mov     rcx, rdi; KeyHandle
0x1800265e5  mov     [rsp+70h+var_50], rax; __int64
0x1800265ea  call    BaseRegOpenClassKey
0x1800265ef  mov     edi, eax
0x1800265f1  test    eax, eax
0x1800265f3  js      short loc_180026628
0x1800265f5  call    IsTermsrvDeleteKeyPresent
0x1800265fa  test    al, al
0x1800265fc  jnz     loc_1800266B5
0x180026602  test    edi, edi
0x180026604  js      short loc_180026628
0x180026606  mov     rcx, [rbp+KeyHandle]; KeyHandle
0x18002660a  call    cs:__imp_NtDeleteKey
0x180026611  nop     dword ptr [rax+rax+00h]
0x180026616  mov     rcx, [rbp+KeyHandle]; Handle
0x18002661a  mov     edi, eax
0x18002661c  call    cs:__imp_NtClose
0x180026623  nop     dword ptr [rax+rax+00h]
0x180026628  mov     ecx, edi; Status
0x18002662a  movdqu  xmmword ptr [rbx], xmm6
0x18002662e  call    cs:__imp_RtlNtStatusToDosError
0x180026635  nop     dword ptr [rax+rax+00h]
0x18002663a  mov     rbx, [rsp+70h+arg_10]
0x180026642  movaps  xmm6, [rsp+70h+var_10]
0x180026647  add     rsp, 70h
0x18002664b  pop     r14
0x18002664d  pop     rdi
0x18002664e  pop     rbp
0x18002664f  retn
0x180026651  call    cs:__imp_RegKrnGetTermsrvRegistryExtensionFlags
0x180026658  nop     dword ptr [rax+rax+00h]
0x18002665d  test    al, 2
0x18002665f  jz      short loc_180026679
0x180026661  mov     rdx, rbx
0x180026664  lea     rcx, [rbp+arg_0]
0x180026668  call    ExtractClassKey
0x18002666d  mov     rdi, [rbp+arg_0]
0x180026671  test    eax, eax
0x180026673  jnz     loc_1800265DB
0x180026679  mov     eax, dword ptr [rbp+arg_0+4]
0x18002667c  lea     r8, [rbp+var_40]; int
0x180026680  xorps   xmm0, xmm0
0x180026683  mov     [rbp+var_40], 30h ; '0'
0x18002668a  mov     edx, 10000h; int
0x18002668f  mov     [rbp+var_38], edi
0x180026692  lea     rcx, [rbp+KeyHandle]; int
0x180026696  mov     [rbp+var_34], eax
0x180026699  movdqu  [rbp+var_20], xmm0
0x18002669e  mov     [rbp+var_28], 40h ; '@'
0x1800266a5  mov     [rbp+var_30], rbx
0x1800266a9  call    Wow64NtOpenKey
0x1800266ae  mov     edi, eax
0x1800266b0  jmp     loc_1800265F5
0x1800266b5  mov     rcx, [rbp+KeyHandle]
0x1800266b9  call    cs:__imp_TermsrvDeleteKey
0x1800266c0  nop     dword ptr [rax+rax+00h]
0x1800266c5  jmp     loc_180026602
0x1800266ca  mov     eax, 57h ; 'W'
0x1800266cf  jmp     loc_18002663A
```
