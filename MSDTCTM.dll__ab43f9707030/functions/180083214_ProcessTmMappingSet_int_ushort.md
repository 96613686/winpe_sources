# ProcessTmMappingSet(int,ushort * *)

- ea: `0x180083214`
- end: `0x180083456`
- name: `?ProcessTmMappingSet@@YAJHPEAPEAG@Z`
- size: `578`
- prototype: `__int64 __fastcall(int, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `6`
- tags: `service_task, broker_com_uri`

## callers

- `0x180010b40`

## callees

- `0x1800063b0`
- `0x18001a134`
- `0x180023160`
- `0x180083214`
- `0x1800846c0`
- `0x1800857c0`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180083445`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180083445`
- `msvcrt!_wcsicmp` at `0x18008329a`
- `msvcrt!_wcsicmp` at `0x1800832ba`
- `msvcrt!_wcsicmp` at `0x1800832f4`
- `msvcrt!_wcsicmp` at `0x180083321`
- `msvcrt!_wcsicmp` at `0x18008335e`
- `msvcrt!_wcsicmp` at `0x1800833a2`
- `msvcrt!_wcsicmp` at `0x18008329a`
- `msvcrt!_wcsicmp` at `0x1800832ba`
- `msvcrt!_wcsicmp` at `0x1800832f4`
- `msvcrt!_wcsicmp` at `0x180083321`
- `msvcrt!_wcsicmp` at `0x18008335e`
- `msvcrt!_wcsicmp` at `0x1800833a2`

## string_xrefs

- `0x180083418`: `com\complus\dtc\dtc\msdtc\src\msdtc.cpp`
- `0x180083232`: `Service`
- `0x18008323d`: `ComplusApp`
- `0x180083252`: `ProcessTmMappingSet (com\complus\dtc\dtc\msdtc\src\msdtc.cpp@824): ProcessTmMappingSet: NULL != argv`
- `0x18008331a`: `-service`
- `0x180083357`: `-complusAppId`

## pseudocode

```c
__int64 __fastcall ProcessTmMappingSet(int a1, unsigned __int16 **a2)
{
  __int64 v4; // r9
  unsigned int v5; // ebx
  __int64 v6; // rsi
  unsigned int v7; // eax
  unsigned __int16 *v8; // rcx
  const BYTE *v9; // r9
  unsigned __int16 *v10; // rdx
  unsigned int v11; // eax
  unsigned __int16 *v13; // [rsp+28h] [rbp-60h]
  unsigned __int16 *v14[9]; // [rsp+40h] [rbp-48h]
  LPVOID pv; // [rsp+98h] [rbp+10h] BYREF

  pv = 0;
  v14[0] = L"Exe";
  v14[1] = L"Service";
  v14[2] = L"ComplusApp";
  if ( !a2 )
    DtcInternalErrorW(L"ProcessTmMappingSet (com\\complus\\dtc\\dtc\\msdtc\\src\\msdtc.cpp@824): ProcessTmMappingSet: NULL != argv");
  if ( (unsigned int)(a1 - 7) <= 1 )
  {
    if ( _wcsicmp(a2[2], L"-name") )
    {
      v4 = 850;
      goto LABEL_34;
    }
    if ( _wcsicmp(a2[4], L"-exe") )
    {
      if ( _wcsicmp(a2[4], L"-service") )
      {
        if ( _wcsicmp(a2[4], L"-complusAppId") )
        {
          v4 = 891;
          goto LABEL_34;
        }
        v6 = 2;
        if ( (int)DuplicateString(L"AppId", (unsigned __int16 **)&pv) < 0 )
        {
          v4 = 884;
          goto LABEL_34;
        }
      }
      else
      {
        if ( (int)DuplicateString(L"Name", (unsigned __int16 **)&pv) < 0 )
        {
          v4 = 872;
          goto LABEL_34;
        }
        v6 = 1;
      }
    }
    else
    {
      if ( (int)DuplicateString(L"Name", (unsigned __int16 **)&pv) < 0 )
      {
        v4 = 861;
        goto LABEL_34;
      }
      v6 = 0;
    }
    if ( _wcsicmp(a2[6], L"-clusterResourceName") )
    {
      if ( _wcsicmp(a2[6], L"-local") )
      {
        v4 = 918;
        goto LABEL_34;
      }
      if ( a1 != 7 )
      {
        v4 = 910;
        goto LABEL_34;
      }
      v7 = 0;
    }
    else
    {
      if ( a1 != 8 )
      {
        v4 = 901;
        goto LABEL_34;
      }
      v7 = 1;
    }
    v8 = v14[v6];
    v9 = (const BYTE *)a2[5];
    v10 = a2[3];
    if ( v7 == 1 )
      v11 = SetClusterTmMapping(v8, v10, (unsigned __int16 *)pv, v9, 1u, a2[7]);
    else
      v11 = SetClusterTmMapping(v8, v10, (unsigned __int16 *)pv, v9, v7, 0);
    v5 = v11;
  }
  else
  {
    if ( a1 != 3 )
    {
      v4 = 832;
LABEL_34:
      LODWORD(v13) = -2147024809;
      v5 = -2147024809;
      TraceStringInline(
        3,
        1,
        L"com\\complus\\dtc\\dtc\\msdtc\\src\\msdtc.cpp",
        v4,
        L"ProcessTmMappingSet",
        v13,
        L"ProcessTmMappingSet: Incorrect usage");
      goto LABEL_35;
    }
    DisplayLocMessageToConsole(0x6Bu);
    v5 = -2147467259;
  }
LABEL_35:
  CoTaskMemFree(pv);
  return v5;
}

```

## disassembly

```asm
0x180083214  mov     r11, rsp
0x180083217  push    rbx
0x180083218  push    rbp
0x180083219  push    rsi
0x18008321a  push    rdi
0x18008321b  sub     rsp, 68h
0x18008321f  mov     qword ptr [r11+10h], 0
0x180083227  lea     rax, aExe; "Exe"
0x18008322e  mov     [r11-48h], rax
0x180083232  lea     rax, aService; "Service"
0x180083239  mov     [r11-40h], rax
0x18008323d  lea     rax, aComplusapp; "ComplusApp"
0x180083244  mov     [r11-38h], rax
0x180083248  mov     rbx, rdx
0x18008324b  mov     edi, ecx
0x18008324d  test    rdx, rdx
0x180083250  jnz     short loc_18008325F
0x180083252  lea     rcx, aProcesstmmappi_4; "ProcessTmMappingSet (com\\complus\\dtc"...
0x180083259  call    ?DtcInternalErrorW@@YAXPEBG@Z; DtcInternalErrorW(ushort const *)
0x18008325f  lea     eax, [rcx-7]
0x180083262  mov     ebp, 1
0x180083267  cmp     eax, ebp
0x180083269  jbe     short loc_18008328F
0x18008326b  cmp     edi, 3
0x18008326e  jz      short loc_18008327B
0x180083270  mov     r9d, 340h
0x180083276  jmp     loc_180083407
0x18008327b  mov     ecx, 6Bh ; 'k'; uID
0x180083280  call    ?DisplayLocMessageToConsole@@YAXI@Z; DisplayLocMessageToConsole(uint)
0x180083285  mov     ebx, 80004005h
0x18008328a  jmp     loc_18008343D
0x18008328f  mov     rcx, [rbx+10h]; String1
0x180083293  lea     rdx, aName_0; "-name"
0x18008329a  call    cs:__imp__wcsicmp
0x1800832a0  test    eax, eax
0x1800832a2  jz      short loc_1800832AF
0x1800832a4  mov     r9d, 352h
0x1800832aa  jmp     loc_180083407
0x1800832af  mov     rcx, [rbx+20h]; String1
0x1800832b3  lea     rdx, aExe_0; "-exe"
0x1800832ba  call    cs:__imp__wcsicmp
0x1800832c0  test    eax, eax
0x1800832c2  jnz     short loc_180083316
0x1800832c4  lea     rdx, [rsp+88h+pv]; unsigned __int16 **
0x1800832cc  lea     rcx, aName; "Name"
0x1800832d3  call    ?DuplicateString@@YAJPEBGPEAPEAG@Z; DuplicateString(ushort const *,ushort * *)
0x1800832d8  test    eax, eax
0x1800832da  jns     short loc_1800832E7
0x1800832dc  mov     r9d, 35Dh
0x1800832e2  jmp     loc_180083407
0x1800832e7  xor     esi, esi
0x1800832e9  mov     rcx, [rbx+30h]; String1
0x1800832ed  lea     rdx, aClusterresourc_0; "-clusterResourceName"
0x1800832f4  call    cs:__imp__wcsicmp
0x1800832fa  test    eax, eax
0x1800832fc  jnz     loc_180083397
0x180083302  cmp     edi, 8
0x180083305  jz      loc_180083393
0x18008330b  mov     r9d, 385h
0x180083311  jmp     loc_180083407
0x180083316  mov     rcx, [rbx+20h]; String1
0x18008331a  lea     rdx, aService_0; "-service"
0x180083321  call    cs:__imp__wcsicmp
0x180083327  test    eax, eax
0x180083329  jnz     short loc_180083353
0x18008332b  lea     rdx, [rsp+88h+pv]; unsigned __int16 **
0x180083333  lea     rcx, aName; "Name"
0x18008333a  call    ?DuplicateString@@YAJPEBGPEAPEAG@Z; DuplicateString(ushort const *,ushort * *)
0x18008333f  test    eax, eax
0x180083341  jns     short loc_18008334E
0x180083343  mov     r9d, 368h
0x180083349  jmp     loc_180083407
0x18008334e  mov     rsi, rbp
0x180083351  jmp     short loc_1800832E9
0x180083353  mov     rcx, [rbx+20h]; String1
0x180083357  lea     rdx, aComplusappid; "-complusAppId"
0x18008335e  call    cs:__imp__wcsicmp
0x180083364  test    eax, eax
0x180083366  jnz     loc_180083401
0x18008336c  lea     rdx, [rsp+88h+pv]; unsigned __int16 **
0x180083374  lea     rcx, aAppid; "AppId"
0x18008337b  lea     esi, [rax+2]
0x18008337e  call    ?DuplicateString@@YAJPEBGPEAPEAG@Z; DuplicateString(ushort const *,ushort * *)
0x180083383  test    eax, eax
0x180083385  jns     loc_1800832E9
0x18008338b  mov     r9d, 374h
0x180083391  jmp     short loc_180083407
0x180083393  mov     eax, ebp
0x180083395  jmp     short loc_1800833BB
0x180083397  mov     rcx, [rbx+30h]; String1
0x18008339b  lea     rdx, aLocal; "-local"
0x1800833a2  call    cs:__imp__wcsicmp
0x1800833a8  test    eax, eax
0x1800833aa  jnz     short loc_1800833F9
0x1800833ac  cmp     edi, 7
0x1800833af  jz      short loc_1800833B9
0x1800833b1  mov     r9d, 38Eh
0x1800833b7  jmp     short loc_180083407
0x1800833b9  xor     eax, eax
0x1800833bb  mov     rcx, [rsp+rsi*8+88h+var_48]; unsigned __int16 *
0x1800833c0  mov     r9, [rbx+28h]; unsigned __int16 *
0x1800833c4  mov     r8, [rsp+88h+pv]; unsigned __int16 *
0x1800833cc  mov     rdx, [rbx+18h]; unsigned __int16 *
0x1800833d0  cmp     eax, ebp
0x1800833d2  jnz     short loc_1800833E3
0x1800833d4  mov     rax, [rbx+38h]
0x1800833d8  mov     [rsp+88h+var_60], rax
0x1800833dd  mov     [rsp+88h+var_68], ebp
0x1800833e1  jmp     short loc_1800833F0
0x1800833e3  mov     [rsp+88h+var_60], 0; unsigned __int16 *
0x1800833ec  mov     [rsp+88h+var_68], eax; unsigned int
0x1800833f0  call    ?SetClusterTmMapping@@YAJPEAG000K0@Z; SetClusterTmMapping(ushort *,ushort *,ushort *,ushort *,ulong,ushort *)
0x1800833f5  mov     ebx, eax
0x1800833f7  jmp     short loc_18008343D
0x1800833f9  mov     r9d, 396h
0x1800833ff  jmp     short loc_180083407
0x180083401  mov     r9d, 37Bh
0x180083407  lea     rcx, aProcesstmmappi; "ProcessTmMappingSet: Incorrect usage"
0x18008340e  mov     eax, 80070057h
0x180083413  mov     [rsp+88h+var_58], rcx
0x180083418  lea     r8, aComComplusDtcD_88; "com\\complus\\dtc\\dtc\\msdtc\\src\\msd"...
0x18008341f  mov     dword ptr [rsp+88h+var_60], eax
0x180083423  mov     ebx, eax
0x180083425  lea     rax, aProcesstmmappi_0; "ProcessTmMappingSet"
0x18008342c  mov     edx, ebp
0x18008342e  mov     ecx, 3
0x180083433  mov     qword ptr [rsp+88h+var_68], rax
0x180083438  call    ?TraceStringInline@@YAXW4TraceSource@@EPEBGK1J1ZZ; TraceStringInline(TraceSource,uchar,ushort const *,ulong,ushort const *,long,ushort const *,...)
0x18008343d  mov     rcx, [rsp+88h+pv]; pv
0x180083445  call    cs:__imp_CoTaskMemFree
0x18008344b  mov     eax, ebx
0x18008344d  add     rsp, 68h
0x180083451  pop     rdi
0x180083452  pop     rsi
0x180083453  pop     rbp
0x180083454  pop     rbx
0x180083455  retn
```
