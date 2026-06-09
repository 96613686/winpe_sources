# SystemRadioChanged(RADIO_SWITCH_CHANGE)

- ea: `0x1800248b0`
- end: `0x180024a40`
- name: `?SystemRadioChanged@@YAXW4RADIO_SWITCH_CHANGE@@@Z`
- size: `400`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x180002ec0`
- `0x180003d50`
- `0x18000d2a0`
- `0x1800241ac`
- `0x1800248b0`
- `0x180028010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180024929`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180024929`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall SystemRadioChanged(unsigned int a1)
{
  HRESULT v2; // eax
  unsigned int v3; // ebx
  __int64 v4; // rdx
  __int64 v5; // r8
  __int64 v6; // rcx
  __int64 v7; // rdx
  LPVOID ppv; // [rsp+30h] [rbp-28h] BYREF
  int v10; // [rsp+38h] [rbp-20h] BYREF

  ppv = 0;
  if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0
    && *(_BYTE *)(WPP_GLOBAL_Control + 25LL) >= 4u )
  {
    WPP_SF_d(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 10, &WPP_a21bdbfcba293ef5dc0b3c60c52e054b_Traceguids, a1);
  }
  v2 = CoCreateInstance(&CLSID_RadioManagementAPI, 0, 4u, &GUID_db3afbfb_08e6_46c6_aa70_bf9a34c30ab7, &ppv);
  if ( v2 < 0 )
  {
    v6 = WPP_GLOBAL_Control;
    if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
      return ATL::CComPtrBase<IUIRadioManager>::~CComPtrBase<IUIRadioManager>(&ppv);
    if ( (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) == 0 || *(_BYTE *)(WPP_GLOBAL_Control + 25LL) < 2u )
      goto LABEL_26;
    v7 = 12;
    goto LABEL_24;
  }
  v10 = 0;
  if ( (*(int (__fastcall **)(LPVOID, int *))(*(_QWORD *)ppv + 24LL))(ppv, &v10) < 0 || !v10 )
    goto LABEL_25;
  if ( a1 )
  {
    v3 = a1 - 1;
    if ( !v3 )
    {
      v4 = 1;
      v5 = 1;
      goto LABEL_15;
    }
    if ( v3 != 1 )
    {
LABEL_25:
      v6 = WPP_GLOBAL_Control;
      goto LABEL_26;
    }
    v4 = 0;
  }
  else
  {
    v4 = 1;
  }
  v5 = 0;
LABEL_15:
  v2 = (*(__int64 (__fastcall **)(LPVOID, __int64, __int64))(*(_QWORD *)ppv + 64LL))(ppv, v4, v5);
  if ( v2 >= 0 )
    goto LABEL_25;
  v6 = WPP_GLOBAL_Control;
  if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
    return ATL::CComPtrBase<IUIRadioManager>::~CComPtrBase<IUIRadioManager>(&ppv);
  if ( (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 && *(_BYTE *)(WPP_GLOBAL_Control + 25LL) >= 2u )
  {
    v7 = 11;
LABEL_24:
    WPP_SF_d(*(_QWORD *)(v6 + 16), v7, &WPP_a21bdbfcba293ef5dc0b3c60c52e054b_Traceguids, (unsigned int)v2);
    goto LABEL_25;
  }
LABEL_26:
  if ( (_UNKNOWN *)v6 != &WPP_GLOBAL_Control && (*(_BYTE *)(v6 + 28) & 1) != 0 && *(_BYTE *)(v6 + 25) >= 4u )
    WPP_SF_(*(_QWORD *)(v6 + 16), 13, &WPP_a21bdbfcba293ef5dc0b3c60c52e054b_Traceguids);
  return ATL::CComPtrBase<IUIRadioManager>::~CComPtrBase<IUIRadioManager>(&ppv);
}

```

## disassembly

```asm
0x1800248b0  mov     [rsp+arg_8], rbx
0x1800248b5  push    rbp
0x1800248b6  sub     rsp, 50h
0x1800248ba  mov     rax, cs:__security_cookie
0x1800248c1  xor     rax, rsp
0x1800248c4  mov     [rsp+58h+var_18], rax
0x1800248c9  mov     ebx, ecx
0x1800248cb  mov     [rsp+58h+var_28], 0
0x1800248d4  lea     rbp, WPP_GLOBAL_Control
0x1800248db  mov     rcx, cs:WPP_GLOBAL_Control
0x1800248e2  cmp     rcx, rbp
0x1800248e5  jz      short loc_18002490B
0x1800248e7  test    byte ptr [rcx+1Ch], 1
0x1800248eb  jz      short loc_18002490B
0x1800248ed  cmp     byte ptr [rcx+19h], 4
0x1800248f1  jb      short loc_18002490B
0x1800248f3  mov     edx, 0Ah
0x1800248f8  mov     r9d, ebx
0x1800248fb  lea     r8, WPP_a21bdbfcba293ef5dc0b3c60c52e054b_Traceguids
0x180024902  mov     rcx, [rcx+10h]
0x180024906  call    WPP_SF_d
0x18002490b  lea     rax, [rsp+58h+var_28]
0x180024910  mov     [rsp+58h+ppv], rax; ppv
0x180024915  lea     r9, _GUID_db3afbfb_08e6_46c6_aa70_bf9a34c30ab7; riid
0x18002491c  xor     edx, edx; pUnkOuter
0x18002491e  lea     r8d, [rdx+4]; dwClsContext
0x180024922  lea     rcx, CLSID_RadioManagementAPI; rclsid
0x180024929  call    cs:__imp_CoCreateInstance
0x18002492f  test    eax, eax
0x180024931  js      loc_1800249C0
0x180024937  mov     [rsp+58h+var_20], 0
0x18002493f  mov     rcx, [rsp+58h+var_28]
0x180024944  mov     rax, [rcx]
0x180024947  lea     rdx, [rsp+58h+var_20]
0x18002494c  mov     rax, [rax+18h]
0x180024950  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024955  test    eax, eax
0x180024957  js      loc_1800249F0
0x18002495d  cmp     [rsp+58h+var_20], 0
0x180024962  jz      loc_1800249F0
0x180024968  test    ebx, ebx
0x18002496a  jz      short loc_180024984
0x18002496c  sub     ebx, 1
0x18002496f  jz      short loc_18002497A
0x180024971  cmp     ebx, 1
0x180024974  jnz     short loc_1800249F0
0x180024976  xor     edx, edx
0x180024978  jmp     short loc_180024989
0x18002497a  mov     edx, 1
0x18002497f  mov     r8d, edx
0x180024982  jmp     short loc_18002498C
0x180024984  mov     edx, 1
0x180024989  xor     r8d, r8d
0x18002498c  mov     rcx, [rsp+58h+var_28]
0x180024991  mov     rax, [rcx]
0x180024994  mov     rax, [rax+40h]
0x180024998  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002499d  test    eax, eax
0x18002499f  jns     short loc_1800249F0
0x1800249a1  mov     rcx, cs:WPP_GLOBAL_Control
0x1800249a8  cmp     rcx, rbp
0x1800249ab  jz      short loc_180024A1E
0x1800249ad  test    byte ptr [rcx+1Ch], 1
0x1800249b1  jz      short loc_1800249F7
0x1800249b3  cmp     byte ptr [rcx+19h], 2
0x1800249b7  jb      short loc_1800249F7
0x1800249b9  mov     edx, 0Bh
0x1800249be  jmp     short loc_1800249DD
0x1800249c0  mov     rcx, cs:WPP_GLOBAL_Control
0x1800249c7  cmp     rcx, rbp
0x1800249ca  jz      short loc_180024A1E
0x1800249cc  test    byte ptr [rcx+1Ch], 1
0x1800249d0  jz      short loc_1800249F7
0x1800249d2  cmp     byte ptr [rcx+19h], 2
0x1800249d6  jb      short loc_1800249F7
0x1800249d8  mov     edx, 0Ch
0x1800249dd  mov     r9d, eax
0x1800249e0  lea     r8, WPP_a21bdbfcba293ef5dc0b3c60c52e054b_Traceguids
0x1800249e7  mov     rcx, [rcx+10h]
0x1800249eb  call    WPP_SF_d
0x1800249f0  mov     rcx, cs:WPP_GLOBAL_Control
0x1800249f7  cmp     rcx, rbp
0x1800249fa  jz      short loc_180024A1E
0x1800249fc  test    byte ptr [rcx+1Ch], 1
0x180024a00  jz      short loc_180024A1E
0x180024a02  cmp     byte ptr [rcx+19h], 4
0x180024a06  jb      short loc_180024A1E
0x180024a08  mov     edx, 0Dh
0x180024a0d  lea     r8, WPP_a21bdbfcba293ef5dc0b3c60c52e054b_Traceguids
0x180024a14  mov     rcx, [rcx+10h]
0x180024a18  call    WPP_SF_
0x180024a1d  nop
0x180024a1e  lea     rcx, [rsp+58h+var_28]
0x180024a23  call    ??1?$CComPtrBase@UIUIRadioManager@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUIRadioManager>::~CComPtrBase<IUIRadioManager>(void)
0x180024a28  mov     rcx, [rsp+58h+var_18]
0x180024a2d  xor     rcx, rsp; StackCookie
0x180024a30  call    __security_check_cookie
0x180024a35  mov     rbx, [rsp+58h+arg_8]
0x180024a3a  add     rsp, 50h
0x180024a3e  pop     rbp
0x180024a3f  retn
```
