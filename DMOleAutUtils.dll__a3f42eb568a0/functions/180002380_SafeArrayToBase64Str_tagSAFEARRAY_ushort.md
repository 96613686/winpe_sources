# SafeArrayToBase64Str(tagSAFEARRAY *,ushort * *)

- ea: `0x180002380`
- end: `0x180002425`
- name: `?SafeArrayToBase64Str@@YAJPEAUtagSAFEARRAY@@PEAPEAG@Z`
- size: `165`
- prototype: `__int64 __fastcall(SAFEARRAY *psa, unsigned __int16 **)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x180002380`

## import_xrefs

- `OLEAUT32!__imp_SafeArrayGetUBound` at `0x1800023d4`
- `OLEAUT32!__imp_SafeArrayGetUBound` at `0x1800023d4`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x1800023bb`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x1800023bb`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x18000240d`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x18000240d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800023fc`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800023fc`
- `DMCmnUtils!EncodeBase64W` at `0x1800023f2`
- `DMCmnUtils!EncodeBase64W` at `0x1800023f2`

## pseudocode

```c
__int64 __fastcall SafeArrayToBase64Str(SAFEARRAY *psa, unsigned __int16 **a2)
{
  HRESULT UBound; // ebx
  LONG plUbound; // [rsp+30h] [rbp+8h] BYREF
  void *ppvData; // [rsp+40h] [rbp+18h] BYREF

  ppvData = 0;
  plUbound = 0;
  if ( psa && a2 )
  {
    UBound = SafeArrayAccessData(psa, &ppvData);
    if ( UBound >= 0 )
    {
      UBound = SafeArrayGetUBound(psa, 1u, &plUbound);
      if ( UBound >= 0 )
        UBound = EncodeBase64W((const unsigned __int8 *)ppvData, ++plUbound, a2);
    }
  }
  else
  {
    UBound = -2147024809;
  }
  LocalFree(0);
  if ( ppvData )
    SafeArrayUnaccessData(psa);
  return (unsigned int)UBound;
}

```

## disassembly

```asm
0x180002380  mov     rax, rsp
0x180002383  mov     [rax+10h], rbx
0x180002387  mov     [rax+20h], rsi
0x18000238b  push    rdi
0x18000238c  sub     rsp, 20h
0x180002390  mov     qword ptr [rax+18h], 0
0x180002398  mov     rsi, rdx
0x18000239b  mov     dword ptr [rax+8], 0
0x1800023a2  mov     rdi, rcx
0x1800023a5  test    rcx, rcx
0x1800023a8  jnz     short loc_1800023B1
0x1800023aa  mov     ebx, 80070057h
0x1800023af  jmp     short loc_1800023FA
0x1800023b1  test    rsi, rsi
0x1800023b4  jz      short loc_1800023AA
0x1800023b6  lea     rdx, [rsp+28h+ppvData]; ppvData
0x1800023bb  call    cs:__imp_SafeArrayAccessData
0x1800023c1  mov     ebx, eax
0x1800023c3  test    eax, eax
0x1800023c5  js      short loc_1800023FA
0x1800023c7  lea     r8, [rsp+28h+plUbound]; plUbound
0x1800023cc  mov     edx, 1; nDim
0x1800023d1  mov     rcx, rdi; psa
0x1800023d4  call    cs:__imp_SafeArrayGetUBound
0x1800023da  mov     ebx, eax
0x1800023dc  test    eax, eax
0x1800023de  js      short loc_1800023FA
0x1800023e0  mov     edx, [rsp+28h+plUbound]
0x1800023e4  mov     r8, rsi
0x1800023e7  mov     rcx, [rsp+28h+ppvData]
0x1800023ec  inc     edx
0x1800023ee  mov     [rsp+28h+plUbound], edx
0x1800023f2  call    cs:__imp_?EncodeBase64W@@YAJPEBEHPEAPEAG@Z; EncodeBase64W(uchar const *,int,ushort * *)
0x1800023f8  mov     ebx, eax
0x1800023fa  xor     ecx, ecx; hMem
0x1800023fc  call    cs:__imp_LocalFree
0x180002402  cmp     [rsp+28h+ppvData], 0
0x180002408  jz      short loc_180002413
0x18000240a  mov     rcx, rdi; psa
0x18000240d  call    cs:__imp_SafeArrayUnaccessData
0x180002413  mov     rsi, [rsp+28h+arg_18]
0x180002418  mov     eax, ebx
0x18000241a  mov     rbx, [rsp+28h+arg_8]
0x18000241f  add     rsp, 20h
0x180002423  pop     rdi
0x180002424  retn
```
