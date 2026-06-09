# SafeArrayToByteArray(tagSAFEARRAY *,uchar * *,ulong *)

- ea: `0x180002430`
- end: `0x18000251f`
- name: `?SafeArrayToByteArray@@YAJPEAUtagSAFEARRAY@@PEAPEAEPEAK@Z`
- size: `239`
- prototype: `__int64 __fastcall(SAFEARRAY *psa, unsigned __int8 **, unsigned int *)`
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x180002430`
- `0x180003574`
- `0x18000361c`

## import_xrefs

- `OLEAUT32!__imp_SafeArrayGetUBound` at `0x180002480`
- `OLEAUT32!__imp_SafeArrayGetUBound` at `0x180002480`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x1800024b9`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x1800024b9`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x1800024f7`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x1800024f7`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180002500`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180002500`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000249c`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000249c`

## pseudocode

```c
__int64 __fastcall SafeArrayToByteArray(SAFEARRAY *psa, unsigned __int8 **a2, unsigned int *a3)
{
  unsigned __int8 *v3; // rdi
  HRESULT UBound; // ebx
  unsigned int v8; // ebp
  __int64 v9; // rcx
  void *v10; // rdx
  LONG plUbound; // [rsp+58h] [rbp+10h] BYREF
  void *ppvData; // [rsp+68h] [rbp+20h] BYREF

  v3 = 0;
  ppvData = 0;
  plUbound = 0;
  if ( !a2 || !a3 || !psa )
  {
    UBound = -2147024809;
    goto LABEL_16;
  }
  UBound = SafeArrayGetUBound(psa, 1u, &plUbound);
  if ( UBound >= 0 )
  {
    v8 = plUbound + 1;
    if ( plUbound == -1 )
    {
LABEL_13:
      *a2 = v3;
      v3 = 0;
      *a3 = v8;
      goto LABEL_14;
    }
    v3 = (unsigned __int8 *)LocalAlloc(0, v8);
    if ( !v3 )
    {
      UBound = -2147024882;
      goto LABEL_14;
    }
    UBound = SafeArrayAccessData(psa, &ppvData);
    if ( UBound >= 0 )
    {
      v10 = ppvData;
      if ( !ppvData )
      {
        MicrosoftTelemetryAssertTriggeredNoArgs(v9);
        v10 = ppvData;
      }
      memcpy_0(v3, v10, v8);
      goto LABEL_13;
    }
  }
LABEL_14:
  if ( ppvData )
    SafeArrayUnaccessData(psa);
LABEL_16:
  LocalFree(v3);
  return (unsigned int)UBound;
}

```

## disassembly

```asm
0x180002430  mov     rax, rsp
0x180002433  mov     [rax+8], rbx
0x180002437  mov     [rax+18h], rbp
0x18000243b  push    rsi
0x18000243c  push    rdi
0x18000243d  push    r12
0x18000243f  push    r14
0x180002441  push    r15
0x180002443  sub     rsp, 20h
0x180002447  xor     edi, edi
0x180002449  mov     qword ptr [rax+20h], 0
0x180002451  mov     [rax+10h], edi
0x180002454  mov     r14, r8
0x180002457  mov     r15, rdx
0x18000245a  mov     rsi, rcx
0x18000245d  test    rdx, rdx
0x180002460  jnz     short loc_18000246C
0x180002462  mov     ebx, 80070057h
0x180002467  jmp     loc_1800024FD
0x18000246c  test    r14, r14
0x18000246f  jz      short loc_180002462
0x180002471  test    rsi, rsi
0x180002474  jz      short loc_180002462
0x180002476  lea     r8, [rsp+48h+plUbound]; plUbound
0x18000247b  mov     edx, 1; nDim
0x180002480  call    cs:__imp_SafeArrayGetUBound
0x180002486  mov     ebx, eax
0x180002488  test    eax, eax
0x18000248a  js      short loc_1800024EC
0x18000248c  mov     ebp, [rsp+48h+plUbound]
0x180002490  add     ebp, 1
0x180002493  jz      short loc_1800024E4
0x180002495  mov     edx, ebp; uBytes
0x180002497  xor     ecx, ecx; uFlags
0x180002499  mov     r12d, ebp
0x18000249c  call    cs:__imp_LocalAlloc
0x1800024a2  mov     rdi, rax
0x1800024a5  test    rax, rax
0x1800024a8  jnz     short loc_1800024B1
0x1800024aa  mov     ebx, 8007000Eh
0x1800024af  jmp     short loc_1800024EC
0x1800024b1  lea     rdx, [rsp+48h+ppvData]; ppvData
0x1800024b6  mov     rcx, rsi; psa
0x1800024b9  call    cs:__imp_SafeArrayAccessData
0x1800024bf  mov     ebx, eax
0x1800024c1  test    eax, eax
0x1800024c3  js      short loc_1800024EC
0x1800024c5  mov     rdx, [rsp+48h+ppvData]
0x1800024ca  test    rdx, rdx
0x1800024cd  jnz     short loc_1800024D9
0x1800024cf  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x1800024d4  mov     rdx, [rsp+48h+ppvData]; Src
0x1800024d9  mov     r8, r12; Size
0x1800024dc  mov     rcx, rdi; void *
0x1800024df  call    memcpy_0
0x1800024e4  mov     [r15], rdi
0x1800024e7  xor     edi, edi
0x1800024e9  mov     [r14], ebp
0x1800024ec  cmp     [rsp+48h+ppvData], 0
0x1800024f2  jz      short loc_1800024FD
0x1800024f4  mov     rcx, rsi; psa
0x1800024f7  call    cs:__imp_SafeArrayUnaccessData
0x1800024fd  mov     rcx, rdi; hMem
0x180002500  call    cs:__imp_LocalFree
0x180002506  mov     rbp, [rsp+48h+arg_10]
0x18000250b  mov     eax, ebx
0x18000250d  mov     rbx, [rsp+48h+arg_0]
0x180002512  add     rsp, 20h
0x180002516  pop     r15
0x180002518  pop     r14
0x18000251a  pop     r12
0x18000251c  pop     rdi
0x18000251d  pop     rsi
0x18000251e  retn
```
