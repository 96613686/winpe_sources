# Base64StrToSafeArray(ushort const *,tagSAFEARRAY * *)

- ea: `0x180001fb0`
- end: `0x1800020ba`
- name: `?Base64StrToSafeArray@@YAJPEBGPEAPEAUtagSAFEARRAY@@@Z`
- size: `266`
- prototype: `__int64 __fastcall(const unsigned __int16 *, struct tagSAFEARRAY **)`
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x180001fb0`
- `0x180003574`
- `0x18000361c`

## import_xrefs

- `OLEAUT32!__imp_SafeArrayCreate` at `0x180002020`
- `OLEAUT32!__imp_SafeArrayCreate` at `0x180002020`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x1800020a5`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x1800020a5`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x18000203c`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x18000203c`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x18000206a`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x18000209c`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x18000206a`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x18000209c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180002087`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180002087`
- `DMCmnUtils!DecodeBase64W` at `0x180001fff`
- `DMCmnUtils!DecodeBase64W` at `0x180001fff`

## pseudocode

```c
__int64 __fastcall Base64StrToSafeArray(const unsigned __int16 *a1, struct tagSAFEARRAY **a2)
{
  SAFEARRAY *v2; // rdi
  HRESULT v4; // ebx
  SAFEARRAY *v5; // rax
  void *v6; // rcx
  void *Src; // [rsp+20h] [rbp-10h] BYREF
  size_t Size; // [rsp+50h] [rbp+20h] BYREF
  void *ppvData; // [rsp+60h] [rbp+30h] BYREF
  SAFEARRAYBOUND rgsabound; // [rsp+68h] [rbp+38h] BYREF

  v2 = 0;
  Src = 0;
  ppvData = 0;
  LODWORD(Size) = 0;
  rgsabound = 0;
  if ( a1 && a2 )
  {
    v4 = DecodeBase64W(a1, (unsigned __int8 **)&Src, (int *)&Size);
    if ( v4 >= 0 )
    {
      rgsabound.lLbound = 0;
      rgsabound.cElements = Size;
      v5 = SafeArrayCreate(0x11u, 1u, &rgsabound);
      v2 = v5;
      if ( v5 )
      {
        v4 = SafeArrayAccessData(v5, &ppvData);
        if ( v4 >= 0 )
        {
          v6 = ppvData;
          if ( !ppvData )
          {
            MicrosoftTelemetryAssertTriggeredNoArgs(0);
            v6 = ppvData;
          }
          memcpy_0(v6, Src, (unsigned int)Size);
          v4 = SafeArrayUnaccessData(v2);
          if ( v4 >= 0 )
          {
            *a2 = v2;
            v2 = 0;
            ppvData = 0;
          }
        }
      }
      else
      {
        v4 = -2147024882;
      }
    }
  }
  else
  {
    v4 = -2147024809;
  }
  LocalFree(Src);
  if ( v2 )
  {
    if ( ppvData )
      SafeArrayUnaccessData(v2);
    SafeArrayDestroy(v2);
  }
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x180001fb0  mov     [rsp-18h+arg_8], rbx
0x180001fb5  push    rbp
0x180001fb6  push    rsi
0x180001fb7  push    rdi
0x180001fb8  mov     rbp, rsp
0x180001fbb  sub     rsp, 30h
0x180001fbf  xor     edi, edi
0x180001fc1  mov     [rbp+Src], 0
0x180001fc9  mov     [rbp+ppvData], 0
0x180001fd1  mov     rsi, rdx
0x180001fd4  mov     dword ptr [rbp+Size], 0
0x180001fdb  mov     qword ptr [rbp+rgsabound.cElements], 0
0x180001fe3  test    rcx, rcx
0x180001fe6  jnz     short loc_180001FF2
0x180001fe8  mov     ebx, 80070057h
0x180001fed  jmp     loc_180002083
0x180001ff2  test    rsi, rsi
0x180001ff5  jz      short loc_180001FE8
0x180001ff7  lea     r8, [rbp+Size]
0x180001ffb  lea     rdx, [rbp+Src]
0x180001fff  call    cs:__imp_?DecodeBase64W@@YAJQEBGPEAPEAEPEAH@Z; DecodeBase64W(ushort const * const,uchar * *,int *)
0x180002005  mov     ebx, eax
0x180002007  test    eax, eax
0x180002009  js      short loc_180002083
0x18000200b  mov     eax, dword ptr [rbp+Size]
0x18000200e  lea     r8, [rbp+rgsabound]; rgsabound
0x180002012  mov     ecx, 11h; vt
0x180002017  mov     [rbp+rgsabound.lLbound], edi
0x18000201a  mov     [rbp+rgsabound.cElements], eax
0x18000201d  lea     edx, [rcx-10h]; cDims
0x180002020  call    cs:__imp_SafeArrayCreate
0x180002026  mov     rdi, rax
0x180002029  test    rax, rax
0x18000202c  jnz     short loc_180002035
0x18000202e  mov     ebx, 8007000Eh
0x180002033  jmp     short loc_180002083
0x180002035  lea     rdx, [rbp+ppvData]; ppvData
0x180002039  mov     rcx, rdi; psa
0x18000203c  call    cs:__imp_SafeArrayAccessData
0x180002042  mov     ebx, eax
0x180002044  test    eax, eax
0x180002046  js      short loc_180002083
0x180002048  mov     rcx, [rbp+ppvData]
0x18000204c  test    rcx, rcx
0x18000204f  jnz     short loc_18000205A
0x180002051  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180002056  mov     rcx, [rbp+ppvData]; void *
0x18000205a  mov     r8d, dword ptr [rbp+Size]; Size
0x18000205e  mov     rdx, [rbp+Src]; Src
0x180002062  call    memcpy_0
0x180002067  mov     rcx, rdi; psa
0x18000206a  call    cs:__imp_SafeArrayUnaccessData
0x180002070  mov     ebx, eax
0x180002072  test    eax, eax
0x180002074  js      short loc_180002083
0x180002076  mov     [rsi], rdi
0x180002079  xor     edi, edi
0x18000207b  mov     [rbp+ppvData], 0
0x180002083  mov     rcx, [rbp+Src]; hMem
0x180002087  call    cs:__imp_LocalFree
0x18000208d  test    rdi, rdi
0x180002090  jz      short loc_1800020AB
0x180002092  cmp     [rbp+ppvData], 0
0x180002097  jz      short loc_1800020A2
0x180002099  mov     rcx, rdi; psa
0x18000209c  call    cs:__imp_SafeArrayUnaccessData
0x1800020a2  mov     rcx, rdi; psa
0x1800020a5  call    cs:__imp_SafeArrayDestroy
0x1800020ab  mov     eax, ebx
0x1800020ad  mov     rbx, [rsp+30h+arg_8]
0x1800020b2  add     rsp, 30h
0x1800020b6  pop     rdi
0x1800020b7  pop     rsi
0x1800020b8  pop     rbp
0x1800020b9  retn
```
