# GetWorkflowAppPropertiesFromDevPropStore(ushort const *,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> &,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> &)

- ea: `0x180023000`
- end: `0x180023370`
- name: `?GetWorkflowAppPropertiesFromDevPropStore@@YAJPEBGAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@1@Z`
- size: `880`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x18001faa0`
- `0x180022f14`

## callees

- `0x180003ca0`
- `0x1800127a4`
- `0x180020e8c`
- `0x180023000`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x18002315e`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x18002315e`
- `api-ms-win-devices-query-l1-1-0!DevGetObjectProperties` at `0x1800230f9`
- `api-ms-win-devices-query-l1-1-0!DevGetObjectProperties` at `0x1800231bb`
- `api-ms-win-devices-query-l1-1-0!DevGetObjectProperties` at `0x1800230f9`
- `api-ms-win-devices-query-l1-1-0!DevGetObjectProperties` at `0x1800231bb`
- `api-ms-win-devices-query-l1-1-0!DevFreeObjectProperties` at `0x180023175`
- `api-ms-win-devices-query-l1-1-0!DevFreeObjectProperties` at `0x180023175`

## string_xrefs

- `0x1800232e7`: `onecoreuap\printscan\print\workflow\broker\common_lib\workflowbrokerutilities.cpp`
- `0x1800232fe`: `onecoreuap\printscan\print\workflow\broker\common_lib\workflowbrokerutilities.cpp`
- `0x180023318`: `onecoreuap\printscan\print\workflow\broker\common_lib\workflowbrokerutilities.cpp`
- `0x18002332f`: `onecoreuap\printscan\print\workflow\broker\common_lib\workflowbrokerutilities.cpp`
- `0x180023346`: `onecoreuap\printscan\print\workflow\broker\common_lib\workflowbrokerutilities.cpp`
- `0x18002335d`: `onecoreuap\printscan\print\workflow\broker\common_lib\workflowbrokerutilities.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall GetWorkflowAppPropertiesFromDevPropStore(__int64 a1)
{
  int ObjectProperties; // eax
  __int64 result; // rax
  const char *v3; // r9
  GUID rguid; // [rsp+68h] [rbp-F0h]
  DEVPROPKEY v5; // [rsp+78h] [rbp-E0h] BYREF
  int v6; // [rsp+8Ch] [rbp-CCh]
  __int64 v7; // [rsp+90h] [rbp-C8h]
  int v8[4]; // [rsp+A0h] [rbp-B8h]
  int v9; // [rsp+B0h] [rbp-A8h]
  int v10; // [rsp+B4h] [rbp-A4h]
  __int64 v11; // [rsp+B8h] [rbp-A0h]
  __int128 v12; // [rsp+C0h] [rbp-98h]
  int v13; // [rsp+D0h] [rbp-88h]
  int v14; // [rsp+D4h] [rbp-84h]
  __int64 v15; // [rsp+D8h] [rbp-80h]
  wil::details::in1diag3 *retaddr; // [rsp+158h] [rbp+0h]

  rguid = 0;
  v5 = DEVPKEY_Device_ContainerId;
  v6 = 0;
  v7 = 0;
  *(_OWORD *)v8 = DEVPKEY_DeviceContainer_DCA_PackageFamilyName;
  v9 = 100;
  v10 = 0;
  v11 = 0;
  v12 = DEVPKEY_DeviceContainer_DCA_AppUserModelID;
  v13 = 104;
  v14 = 0;
  v15 = 0;
  ObjectProperties = DevGetObjectProperties(1, a1, 0);
  try
  {
    if ( ObjectProperties >= 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0xC9,
        (unsigned int)"onecoreuap\\printscan\\print\\workflow\\broker\\common_lib\\workflowbrokerutilities.cpp",
        (const char *)0x8000FFFFLL,
        (int)&v5);
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0xC6,
      (unsigned int)"onecoreuap\\printscan\\print\\workflow\\broker\\common_lib\\workflowbrokerutilities.cpp",
      (const char *)(unsigned int)ObjectProperties,
      (int)&v5);
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0xEB,
                           (unsigned int)"onecoreuap\\printscan\\print\\workflow\\broker\\common_lib\\workflowbrokerutilities.cpp",
                           v3);
  }
  return result;
}

```

## disassembly

```asm
0x180023000  mov     r11, rsp
0x180023003  mov     [r11+20h], rbx
0x180023007  push    rsi
0x180023008  push    rdi
0x180023009  push    r14
0x18002300b  sub     rsp, 140h
0x180023012  mov     rax, cs:__security_cookie
0x180023019  xor     rax, rsp
0x18002301c  mov     [rsp+158h+var_28], rax
0x180023024  mov     rsi, r8
0x180023027  mov     rdi, rdx
0x18002302a  xor     r14d, r14d
0x18002302d  mov     [rsp+158h+var_110], r14
0x180023032  mov     [rsp+158h+var_118], r14d
0x180023037  xorps   xmm0, xmm0
0x18002303a  movups  xmmword ptr [rsp+158h+rguid.Data1], xmm0
0x18002303f  mov     [rsp+158h+var_108], r14
0x180023044  mov     [rsp+158h+var_100], r14d
0x180023049  mov     eax, dword ptr [rsp+158h+rguid.Data4+4]
0x18002304d  mov     [rsp+158h+var_FC], eax
0x180023051  mov     [rsp+158h+var_F8], 1
0x180023056  movups  xmm0, xmmword ptr cs:DEVPKEY_Device_ContainerId.fmtid.Data1
0x18002305d  movups  xmmword ptr [rsp+158h+var_E0], xmm0
0x180023062  mov     eax, cs:DEVPKEY_Device_ContainerId.pid
0x180023068  mov     [rsp+158h+var_D0], eax
0x18002306f  mov     [r11-0CCh], r14d
0x180023076  mov     [r11-0C8h], r14
0x18002307d  movups  xmm0, cs:DEVPKEY_DeviceContainer_DCA_PackageFamilyName
0x180023084  movaps  xmmword ptr [rsp+158h+var_B8], xmm0
0x18002308c  mov     eax, cs:dword_180069328
0x180023092  mov     [rsp+158h+var_A8], eax
0x180023099  mov     [r11-0A4h], r14d
0x1800230a0  mov     [r11-0A0h], r14
0x1800230a7  movups  xmm0, cs:DEVPKEY_DeviceContainer_DCA_AppUserModelID
0x1800230ae  movaps  [rsp+158h+var_98], xmm0
0x1800230b6  mov     eax, cs:dword_180069310
0x1800230bc  mov     [rsp+158h+var_88], eax
0x1800230c3  mov     [r11-84h], r14d
0x1800230ca  mov     [r11-80h], r14
0x1800230ce  lea     rax, [rsp+158h+var_110]
0x1800230d3  mov     [rsp+158h+var_128], rax
0x1800230d8  lea     rax, [rsp+158h+var_118]
0x1800230dd  mov     [rsp+158h+var_130], rax
0x1800230e2  lea     rax, [rsp+158h+var_E0]
0x1800230e7  mov     qword ptr [rsp+158h+var_138], rax; int
0x1800230ec  lea     r9d, [r14+1]
0x1800230f0  xor     r8d, r8d
0x1800230f3  mov     rdx, rcx
0x1800230f6  mov     ecx, r9d
0x1800230f9  call    cs:__imp_DevGetObjectProperties
0x1800230ff  mov     rcx, [rsp+158h]; this
0x180023107  test    eax, eax
0x180023109  js      loc_1800232E4
0x18002310f  mov     rax, [rsp+158h+var_110]
0x180023114  cmp     [rsp+158h+var_118], 1
0x180023119  jnz     short loc_180023123
0x18002311b  cmp     dword ptr [rax+20h], 0Dh
0x18002311f  mov     cl, 1
0x180023121  jz      short loc_180023126
0x180023123  mov     cl, r14b
0x180023126  mov     r10, [rsp+158h]
0x18002312e  test    cl, cl
0x180023130  jz      loc_1800232F8
0x180023136  mov     rax, [rax+28h]
0x18002313a  movups  xmm0, xmmword ptr [rax]
0x18002313d  movdqu  xmmword ptr [rsp+158h+rguid.Data1], xmm0
0x180023143  mov     rbx, [rsp+158h]
0x18002314b  mov     r8d, 28h ; '('; cchMax
0x180023151  lea     rdx, [rsp+158h+sz]; lpsz
0x180023159  lea     rcx, [rsp+158h+rguid]; rguid
0x18002315e  call    cs:__imp_StringFromGUID2
0x180023164  test    eax, eax
0x180023166  jz      loc_180023312
0x18002316c  mov     rdx, [rsp+158h+var_110]
0x180023171  mov     ecx, [rsp+158h+var_118]
0x180023175  call    cs:__imp_DevFreeObjectProperties
0x18002317b  mov     [rsp+158h+var_110], r14
0x180023180  mov     [rsp+158h+var_118], r14d
0x180023185  lea     rax, [rsp+158h+var_110]
0x18002318a  mov     [rsp+158h+var_128], rax
0x18002318f  lea     rax, [rsp+158h+var_118]
0x180023194  mov     [rsp+158h+var_130], rax
0x180023199  lea     rax, [rsp+158h+var_B8]
0x1800231a1  mov     qword ptr [rsp+158h+var_138], rax; int
0x1800231a6  mov     ebx, 2
0x1800231ab  mov     r9d, ebx
0x1800231ae  xor     r8d, r8d
0x1800231b1  lea     rdx, [rsp+158h+sz]
0x1800231b9  mov     ecx, ebx
0x1800231bb  call    cs:__imp_DevGetObjectProperties
0x1800231c1  mov     rcx, [rsp+158h]; this
0x1800231c9  test    eax, eax
0x1800231cb  js      loc_18002332C
0x1800231d1  cmp     [rsp+158h+var_118], ebx
0x1800231d5  setz    al
0x1800231d8  mov     rcx, [rsp+158h]; this
0x1800231e0  test    al, al
0x1800231e2  jz      loc_180023340
0x1800231e8  mov     ebx, r14d
0x1800231eb  mov     r8, qword ptr cs:DEVPKEY_DeviceContainer_DCA_PackageFamilyName+8
0x1800231f2  mov     r9, qword ptr cs:DEVPKEY_DeviceContainer_DCA_PackageFamilyName
0x1800231f9  mov     r10, qword ptr cs:DEVPKEY_DeviceContainer_DCA_AppUserModelID+8
0x180023200  mov     r11, qword ptr cs:DEVPKEY_DeviceContainer_DCA_AppUserModelID
0x180023207  cmp     ebx, [rsp+158h+var_118]
0x18002320b  jnb     loc_1800232B8
0x180023211  mov     eax, ebx
0x180023213  lea     rdx, [rax+rax*2]
0x180023217  add     rdx, rdx
0x18002321a  mov     rax, [rsp+158h+var_110]
0x18002321f  mov     rcx, [rsp+158h]; this
0x180023227  cmp     dword ptr [rax+rdx*8+20h], 2012h
0x18002322f  jnz     loc_180023357
0x180023235  cmp     dword ptr [rax+rdx*8+10h], 64h ; 'd'
0x18002323a  jnz     short loc_180023266
0x18002323c  cmp     r9, [rax+rdx*8]
0x180023240  jnz     short loc_1800232B1
0x180023242  cmp     r8, [rax+rdx*8+8]
0x180023247  jnz     short loc_1800232B1
0x180023249  mov     rdx, [rax+rdx*8+28h]
0x18002324e  or      r8, 0FFFFFFFFFFFFFFFFh
0x180023252  inc     r8
0x180023255  cmp     [rdx+r8*2], r14w
0x18002325a  jnz     short loc_180023252
0x18002325c  mov     rcx, rdi
0x18002325f  call    ??$_Assign@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Assign<ushort>(ushort const * const,unsigned __int64)
0x180023264  jmp     short loc_180023295
0x180023266  cmp     dword ptr [rax+rdx*8+10h], 68h ; 'h'
0x18002326b  jnz     short loc_1800232B1
0x18002326d  cmp     r11, [rax+rdx*8]
0x180023271  jnz     short loc_1800232B1
0x180023273  cmp     r10, [rax+rdx*8+8]
0x180023278  jnz     short loc_1800232B1
0x18002327a  mov     rdx, [rax+rdx*8+28h]
0x18002327f  or      r8, 0FFFFFFFFFFFFFFFFh
0x180023283  inc     r8
0x180023286  cmp     [rdx+r8*2], r14w
0x18002328b  jnz     short loc_180023283
0x18002328d  mov     rcx, rsi
0x180023290  call    ??$_Assign@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Assign<ushort>(ushort const * const,unsigned __int64)
0x180023295  mov     r11, qword ptr cs:DEVPKEY_DeviceContainer_DCA_AppUserModelID
0x18002329c  mov     r10, qword ptr cs:DEVPKEY_DeviceContainer_DCA_AppUserModelID+8
0x1800232a3  mov     r9, qword ptr cs:DEVPKEY_DeviceContainer_DCA_PackageFamilyName
0x1800232aa  mov     r8, qword ptr cs:DEVPKEY_DeviceContainer_DCA_PackageFamilyName+8
0x1800232b1  inc     ebx
0x1800232b3  jmp     loc_180023207
0x1800232b8  xor     eax, eax
0x1800232ba  jmp     short loc_1800232C0
0x1800232bc  mov     eax, [rsp+158h+var_118]
0x1800232c0  mov     rcx, [rsp+158h+var_28]
0x1800232c8  xor     rcx, rsp; StackCookie
0x1800232cb  call    __security_check_cookie
0x1800232d0  mov     rbx, [rsp+158h+arg_18]
0x1800232d8  add     rsp, 140h
0x1800232df  pop     r14
0x1800232e1  pop     rdi
0x1800232e2  pop     rsi
0x1800232e3  retn
0x1800232e4  mov     r9d, eax; char *
0x1800232e7  lea     r8, aOnecoreuapPrin_29; "onecoreuap\\printscan\\print\\workflow"...
0x1800232ee  mov     edx, 0C6h; void *
0x1800232f3  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800232f8  mov     r9d, 8000FFFFh; char *
0x1800232fe  lea     r8, aOnecoreuapPrin_29; "onecoreuap\\printscan\\print\\workflow"...
0x180023305  mov     edx, 0C9h; void *
0x18002330a  mov     rcx, r10; this
0x18002330d  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180023312  mov     r9d, 8000FFFFh; char *
0x180023318  lea     r8, aOnecoreuapPrin_29; "onecoreuap\\printscan\\print\\workflow"...
0x18002331f  mov     edx, 0CDh; void *
0x180023324  mov     rcx, rbx; this
0x180023327  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18002332c  mov     r9d, eax; char *
0x18002332f  lea     r8, aOnecoreuapPrin_29; "onecoreuap\\printscan\\print\\workflow"...
0x180023336  mov     edx, 0D6h; void *
0x18002333b  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180023340  mov     r9d, 8000FFFFh; char *
0x180023346  lea     r8, aOnecoreuapPrin_29; "onecoreuap\\printscan\\print\\workflow"...
0x18002334d  mov     edx, 0D9h; void *
0x180023352  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180023357  mov     r9d, 80070057h; char *
0x18002335d  lea     r8, aOnecoreuapPrin_29; "onecoreuap\\printscan\\print\\workflow"...
0x180023364  mov     edx, 0DDh; void *
0x180023369  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```
