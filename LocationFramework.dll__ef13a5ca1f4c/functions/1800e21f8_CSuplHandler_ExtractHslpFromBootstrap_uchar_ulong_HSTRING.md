# CSuplHandler::ExtractHslpFromBootstrap(uchar *,ulong,HSTRING__ * *)

- ea: `0x1800e21f8`
- end: `0x1800e2539`
- name: `?ExtractHslpFromBootstrap@CSuplHandler@@CAJPEAEKPEAPEAUHSTRING__@@@Z`
- size: `833`
- prototype: `static int(unsigned __int8 *, unsigned int, HSTRING *)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800e1b3c`

## callees

- `0x180012398`
- `0x1800a98c0`
- `0x1800e21f8`
- `0x18015e010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800e239e`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800e23b8`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800e23d3`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800e2450`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800e2465`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800e2486`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800e249b`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800e24b5`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800e24cd`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800e24e7`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800e239e`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800e23b8`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800e23d3`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800e2450`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800e2465`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800e2486`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800e249b`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800e24b5`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800e24cd`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800e24e7`
- `api-ms-win-core-com-l1-1-0!CreateStreamOnHGlobal` at `0x1800e22a6`
- `api-ms-win-core-com-l1-1-0!CreateStreamOnHGlobal` at `0x1800e22a6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x1800e250b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x1800e250b`
- `XmlLite!CreateXmlReader` at `0x1800e2312`
- `XmlLite!CreateXmlReader` at `0x1800e2312`
- `dmxmlhelputils!WSPFreeBuffer` at `0x1800e2245`
- `dmxmlhelputils!WSPFreeBuffer` at `0x1800e2245`
- `dmxmlhelputils!WBXMLToTextXMLGeneric` at `0x1800e228b`
- `dmxmlhelputils!WBXMLToTextXMLGeneric` at `0x1800e228b`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CSuplHandler::ExtractHslpFromBootstrap(unsigned __int8 *a1, __int64 a2, HSTRING *a3)
{
  unsigned int v4; // r10d
  HRESULT v5; // edi
  __int64 v7; // r8
  unsigned int v8; // ebx
  int v9; // eax
  unsigned int (*i)(void); // rax
  __int64 v11; // rdx
  PCNZWCH sourceString; // [rsp+30h] [rbp-40h] BYREF
  __int64 v13; // [rsp+38h] [rbp-38h] BYREF
  __int64 v14; // [rsp+40h] [rbp-30h] BYREF
  __int64 v15; // [rsp+48h] [rbp-28h]
  void *ppvObject; // [rsp+50h] [rbp-20h] BYREF
  LPSTREAM ppstm; // [rsp+58h] [rbp-18h] BYREF
  int v18; // [rsp+60h] [rbp-10h] BYREF
  int v19; // [rsp+64h] [rbp-Ch] BYREF

  v15 = 0;
  ppstm = 0;
  ppvObject = 0;
  do
  {
    if ( !(_DWORD)a2 )
    {
      v5 = -2147024809;
      goto LABEL_5;
    }
    v4 = a2;
    a2 = (unsigned int)(a2 - 1);
  }
  while ( a1[a2] == 0xFF );
  v5 = WBXMLToTextXMLGeneric(a1, v4, 11);
  if ( v5 >= 0 )
  {
    v18 = 0;
    v5 = CreateStreamOnHGlobal(0, 1, &ppstm);
    if ( v5 >= 0 )
    {
      v7 = -1;
      do
        ++v7;
      while ( *(_BYTE *)(v15 + v7) );
      v5 = (*(__int64 (__fastcall **)(LPSTREAM, __int64, __int64, int *))(*(_QWORD *)ppstm + 32LL))(
             ppstm,
             v15,
             v7,
             &v18);
      if ( v5 >= 0 )
      {
        v5 = (*(__int64 (__fastcall **)(LPSTREAM, _QWORD, _QWORD, _QWORD))(*(_QWORD *)ppstm + 40LL))(ppstm, 0, 0, 0);
        if ( v5 >= 0 )
        {
          v5 = CreateXmlReader(&GUID_7279fc81_709d_4095_b63d_69fe4b0d9030, &ppvObject, 0);
          if ( v5 >= 0 )
          {
            v5 = (*(__int64 (__fastcall **)(void *, LPSTREAM))(*(_QWORD *)ppvObject + 24LL))(ppvObject, ppstm);
            if ( v5 >= 0 )
            {
              v8 = 0;
              while ( 1 )
              {
                v19 = 0;
                v13 = 0;
                v9 = (*(__int64 (__fastcall **)(void *, int *))(*(_QWORD *)ppvObject + 48LL))(ppvObject, &v19);
                v5 = v9;
                if ( v9 < 0 )
                  break;
                if ( v9 == 1 )
                  break;
                v5 = (*(__int64 (__fastcall **)(void *, __int64 *, _QWORD))(*(_QWORD *)ppvObject + 112LL))(
                       ppvObject,
                       &v13,
                       0);
                if ( v5 < 0 )
                  break;
                if ( !(unsigned int)_o__wcsicmp(v13, L"wap-provisioningdoc") )
                  v8 = (v8 & 1) == 0;
                if ( !(unsigned int)_o__wcsicmp(v13, L"characteristic") )
                  v8 = (v8 ^ 2) & 0xFFFFFFC3;
                if ( !(unsigned int)_o__wcsicmp(v13, L"parm") )
                  v8 = (v8 ^ 8) & 0xFFFFFFCF;
                for ( i = *(unsigned int (**)(void))(*(_QWORD *)ppvObject + 64LL);
                      !i();
                      i = *(unsigned int (**)(void))(*(_QWORD *)ppvObject + 72LL) )
                {
                  v14 = 0;
                  sourceString = 0;
                  v5 = (*(__int64 (__fastcall **)(void *, __int64 *, _QWORD))(*(_QWORD *)ppvObject + 112LL))(
                         ppvObject,
                         &v14,
                         0);
                  if ( v5 < 0 )
                    goto LABEL_5;
                  v5 = (*(__int64 (__fastcall **)(void *, PCNZWCH *, _QWORD))(*(_QWORD *)ppvObject + 128LL))(
                         ppvObject,
                         &sourceString,
                         0);
                  if ( v5 < 0 )
                    goto LABEL_5;
                  if ( (v8 & 2) != 0
                    && !(unsigned int)_o__wcsicmp(v14, L"type")
                    && !(unsigned int)_o__wcsicmp(sourceString, L"application") )
                  {
                    v8 |= 4u;
                  }
                  if ( (v8 & 8) != 0 )
                  {
                    if ( !(unsigned int)_o__wcsicmp(v14, L"name") )
                    {
                      if ( (unsigned int)_o__wcsicmp(sourceString, L"APPID") )
                      {
                        if ( !(unsigned int)_o__wcsicmp(sourceString, L"ADDR") )
                          v8 |= 0x20u;
                      }
                      else
                      {
                        v8 |= 0x10u;
                      }
                    }
                    if ( !(unsigned int)_o__wcsicmp(v14, L"value") )
                    {
                      if ( (v8 & 0x10) != 0 && (unsigned int)_o__wcsicmp(sourceString, L"ap0004") )
                      {
                        v5 = -2147467259;
                        goto LABEL_5;
                      }
                      if ( (v8 & 0x20) != 0 )
                      {
                        v11 = -1;
                        do
                          ++v11;
                        while ( sourceString[v11] );
                        WindowsCreateString(sourceString, v11, a3);
                      }
                    }
                  }
                }
              }
            }
          }
        }
      }
    }
  }
LABEL_5:
  WSPFreeBuffer(v15, 1);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&ppvObject);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&ppstm);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x1800e21f8  push    rbp
0x1800e21fa  push    rbx
0x1800e21fb  push    rsi
0x1800e21fc  push    rdi
0x1800e21fd  push    r14
0x1800e21ff  mov     rbp, rsp
0x1800e2202  sub     rsp, 70h
0x1800e2206  mov     rax, cs:__security_cookie
0x1800e220d  xor     rax, rsp
0x1800e2210  mov     [rbp+var_8], rax
0x1800e2214  mov     rsi, r8
0x1800e2217  xor     r14d, r14d
0x1800e221a  mov     [rbp+var_28], r14
0x1800e221e  mov     [rbp+ppstm], r14
0x1800e2222  mov     [rbp+ppvObject], r14
0x1800e2226  jmp     short loc_1800E2233
0x1800e2228  mov     r10d, edx
0x1800e222b  dec     edx
0x1800e222d  cmp     byte ptr [rdx+rcx], 0FFh
0x1800e2231  jnz     short loc_1800E2278
0x1800e2233  test    edx, edx
0x1800e2235  jnz     short loc_1800E2228
0x1800e2237  mov     edi, 80070057h
0x1800e223c  mov     edx, 1
0x1800e2241  mov     rcx, [rbp+var_28]
0x1800e2245  call    cs:__imp_WSPFreeBuffer
0x1800e224b  nop
0x1800e224c  lea     rcx, [rbp+ppvObject]
0x1800e2250  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x1800e2255  nop
0x1800e2256  lea     rcx, [rbp+ppstm]
0x1800e225a  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x1800e225f  mov     eax, edi
0x1800e2261  mov     rcx, [rbp+var_8]
0x1800e2265  xor     rcx, rsp; StackCookie
0x1800e2268  call    __security_check_cookie
0x1800e226d  add     rsp, 70h
0x1800e2271  pop     r14
0x1800e2273  pop     rdi
0x1800e2274  pop     rsi
0x1800e2275  pop     rbx
0x1800e2276  pop     rbp
0x1800e2277  retn
0x1800e2278  lea     rax, [rbp+var_28]
0x1800e227c  mov     [rsp+70h+var_50], rax
0x1800e2281  xor     r9d, r9d
0x1800e2284  lea     r8d, [r9+0Bh]
0x1800e2288  mov     edx, r10d
0x1800e228b  call    cs:__imp_WBXMLToTextXMLGeneric
0x1800e2291  mov     edi, eax
0x1800e2293  test    eax, eax
0x1800e2295  js      short loc_1800E223C
0x1800e2297  mov     [rbp+var_10], r14d
0x1800e229b  lea     r8, [rbp+ppstm]; ppstm
0x1800e229f  mov     edx, 1; fDeleteOnRelease
0x1800e22a4  xor     ecx, ecx; hGlobal
0x1800e22a6  call    cs:__imp_CreateStreamOnHGlobal
0x1800e22ac  mov     edi, eax
0x1800e22ae  test    eax, eax
0x1800e22b0  js      short loc_1800E223C
0x1800e22b2  mov     rcx, [rbp+ppstm]
0x1800e22b6  mov     rax, [rcx]
0x1800e22b9  mov     rdx, [rbp+var_28]
0x1800e22bd  or      r8, 0FFFFFFFFFFFFFFFFh
0x1800e22c1  inc     r8
0x1800e22c4  cmp     [rdx+r8], r14b
0x1800e22c8  jnz     short loc_1800E22C1
0x1800e22ca  lea     r9, [rbp+var_10]
0x1800e22ce  mov     rax, [rax+20h]
0x1800e22d2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e22d7  mov     edi, eax
0x1800e22d9  test    eax, eax
0x1800e22db  js      loc_1800E223C
0x1800e22e1  mov     rcx, [rbp+ppstm]
0x1800e22e5  mov     rdx, r14
0x1800e22e8  mov     rax, [rcx]
0x1800e22eb  xor     r9d, r9d
0x1800e22ee  xor     r8d, r8d
0x1800e22f1  mov     rax, [rax+28h]
0x1800e22f5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e22fa  mov     edi, eax
0x1800e22fc  test    eax, eax
0x1800e22fe  js      loc_1800E223C
0x1800e2304  xor     r8d, r8d; pMalloc
0x1800e2307  lea     rdx, [rbp+ppvObject]; ppvObject
0x1800e230b  lea     rcx, _GUID_7279fc81_709d_4095_b63d_69fe4b0d9030; riid
0x1800e2312  call    cs:__imp_CreateXmlReader
0x1800e2318  mov     edi, eax
0x1800e231a  test    eax, eax
0x1800e231c  js      loc_1800E223C
0x1800e2322  mov     rcx, [rbp+ppvObject]
0x1800e2326  mov     rax, [rcx]
0x1800e2329  mov     rdx, [rbp+ppstm]
0x1800e232d  mov     rax, [rax+18h]
0x1800e2331  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e2336  mov     edi, eax
0x1800e2338  test    eax, eax
0x1800e233a  js      loc_1800E223C
0x1800e2340  mov     ebx, r14d
0x1800e2343  mov     [rbp+var_C], r14d
0x1800e2347  mov     [rbp+var_38], r14
0x1800e234b  mov     rcx, [rbp+ppvObject]
0x1800e234f  mov     rax, [rcx]
0x1800e2352  lea     rdx, [rbp+var_C]
0x1800e2356  mov     rax, [rax+30h]
0x1800e235a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e235f  mov     edi, eax
0x1800e2361  test    eax, eax
0x1800e2363  js      loc_1800E223C
0x1800e2369  cmp     eax, 1
0x1800e236c  jz      loc_1800E223C
0x1800e2372  mov     rcx, [rbp+ppvObject]
0x1800e2376  mov     rax, [rcx]
0x1800e2379  xor     r8d, r8d
0x1800e237c  lea     rdx, [rbp+var_38]
0x1800e2380  mov     rax, [rax+70h]
0x1800e2384  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e2389  mov     edi, eax
0x1800e238b  test    eax, eax
0x1800e238d  js      loc_1800E223C
0x1800e2393  lea     rdx, aWapProvisionin; "wap-provisioningdoc"
0x1800e239a  mov     rcx, [rbp+var_38]
0x1800e239e  call    cs:__imp__o__wcsicmp
0x1800e23a4  test    eax, eax
0x1800e23a6  jnz     short loc_1800E23AD
0x1800e23a8  not     ebx
0x1800e23aa  and     ebx, 1
0x1800e23ad  lea     rdx, aCharacteristic; "characteristic"
0x1800e23b4  mov     rcx, [rbp+var_38]
0x1800e23b8  call    cs:__imp__o__wcsicmp
0x1800e23be  test    eax, eax
0x1800e23c0  jnz     short loc_1800E23C8
0x1800e23c2  xor     ebx, 2
0x1800e23c5  and     ebx, 0FFFFFFC3h
0x1800e23c8  lea     rdx, aParm; "parm"
0x1800e23cf  mov     rcx, [rbp+var_38]
0x1800e23d3  call    cs:__imp__o__wcsicmp
0x1800e23d9  test    eax, eax
0x1800e23db  jnz     short loc_1800E23E3
0x1800e23dd  xor     ebx, 8
0x1800e23e0  and     ebx, 0FFFFFFCFh
0x1800e23e3  mov     rcx, [rbp+ppvObject]
0x1800e23e7  mov     rax, [rcx]
0x1800e23ea  mov     rax, [rax+40h]
0x1800e23ee  jmp     loc_1800E251C
0x1800e23f3  mov     [rbp+var_30], r14
0x1800e23f7  mov     [rbp+sourceString], r14
0x1800e23fb  mov     rcx, [rbp+ppvObject]
0x1800e23ff  mov     rax, [rcx]
0x1800e2402  xor     r8d, r8d
0x1800e2405  lea     rdx, [rbp+var_30]
0x1800e2409  mov     rax, [rax+70h]
0x1800e240d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e2412  mov     edi, eax
0x1800e2414  test    eax, eax
0x1800e2416  js      loc_1800E223C
0x1800e241c  mov     rcx, [rbp+ppvObject]
0x1800e2420  mov     rax, [rcx]
0x1800e2423  xor     r8d, r8d
0x1800e2426  lea     rdx, [rbp+sourceString]
0x1800e242a  mov     rax, [rax+80h]
0x1800e2431  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e2436  mov     edi, eax
0x1800e2438  test    eax, eax
0x1800e243a  js      loc_1800E223C
0x1800e2440  test    bl, 2
0x1800e2443  jz      short loc_1800E2472
0x1800e2445  lea     rdx, aType; "type"
0x1800e244c  mov     rcx, [rbp+var_30]
0x1800e2450  call    cs:__imp__o__wcsicmp
0x1800e2456  test    eax, eax
0x1800e2458  jnz     short loc_1800E2472
0x1800e245a  lea     rdx, aApplication; "application"
0x1800e2461  mov     rcx, [rbp+sourceString]
0x1800e2465  call    cs:__imp__o__wcsicmp
0x1800e246b  test    eax, eax
0x1800e246d  jnz     short loc_1800E2472
0x1800e246f  or      ebx, 4
0x1800e2472  test    bl, 8
0x1800e2475  jz      loc_1800E2511
0x1800e247b  lea     rdx, aName_1; "name"
0x1800e2482  mov     rcx, [rbp+var_30]
0x1800e2486  call    cs:__imp__o__wcsicmp
0x1800e248c  test    eax, eax
0x1800e248e  jnz     short loc_1800E24C2
0x1800e2490  lea     rdx, aAppid; "APPID"
0x1800e2497  mov     rcx, [rbp+sourceString]
0x1800e249b  call    cs:__imp__o__wcsicmp
0x1800e24a1  test    eax, eax
0x1800e24a3  jnz     short loc_1800E24AA
0x1800e24a5  or      ebx, 10h
0x1800e24a8  jmp     short loc_1800E24C2
0x1800e24aa  lea     rdx, aAddr_0; "ADDR"
0x1800e24b1  mov     rcx, [rbp+sourceString]
0x1800e24b5  call    cs:__imp__o__wcsicmp
0x1800e24bb  test    eax, eax
0x1800e24bd  jnz     short loc_1800E24C2
0x1800e24bf  or      ebx, 20h
0x1800e24c2  lea     rdx, aValue_0; "value"
0x1800e24c9  mov     rcx, [rbp+var_30]
0x1800e24cd  call    cs:__imp__o__wcsicmp
0x1800e24d3  test    eax, eax
0x1800e24d5  jnz     short loc_1800E2511
0x1800e24d7  test    bl, 10h
0x1800e24da  jz      short loc_1800E24F1
0x1800e24dc  lea     rdx, aAp0004; "ap0004"
0x1800e24e3  mov     rcx, [rbp+sourceString]
0x1800e24e7  call    cs:__imp__o__wcsicmp
0x1800e24ed  test    eax, eax
0x1800e24ef  jnz     short loc_1800E252E
0x1800e24f1  test    bl, 20h
0x1800e24f4  jz      short loc_1800E2511
0x1800e24f6  mov     rcx, [rbp+sourceString]; sourceString
0x1800e24fa  or      rdx, 0FFFFFFFFFFFFFFFFh
0x1800e24fe  inc     rdx; length
0x1800e2501  cmp     [rcx+rdx*2], r14w
0x1800e2506  jnz     short loc_1800E24FE
0x1800e2508  mov     r8, rsi; string
0x1800e250b  call    cs:__imp_WindowsCreateString
0x1800e2511  mov     rcx, [rbp+ppvObject]
0x1800e2515  mov     rax, [rcx]
0x1800e2518  mov     rax, [rax+48h]
0x1800e251c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e2521  test    eax, eax
0x1800e2523  jz      loc_1800E23F3
0x1800e2529  jmp     loc_1800E2343
0x1800e252e  mov     edi, 80004005h
0x1800e2533  jmp     loc_1800E223C
```
