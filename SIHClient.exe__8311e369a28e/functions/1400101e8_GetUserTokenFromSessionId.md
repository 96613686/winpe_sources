# GetUserTokenFromSessionId

- ea: `0x1400101e8`
- end: `0x140010361`
- name: `GetUserTokenFromSessionId`
- size: `377`
- prototype: ``
- caller_count: `3`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x1400198ac`
- `0x1400309d8`
- `0x1400388e0`

## callees

- `0x140008de4`
- `0x1400101e8`
- `0x140010368`
- `0x140010a58`
- `0x1400190c0`
- `0x14001912c`
- `0x140045dc0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400102e4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400102e4`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14001026e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400102a9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140010340`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14001026e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400102a9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140010340`

## string_xrefs

- `0x1400102d0`: `C:\__w\1\s\src\Client\lib\util\SecurityUtil.cpp`
- `0x140010315`: `C:\__w\1\s\src\Client\lib\util\SecurityUtil.cpp`

## pseudocode

```c
__int64 __fastcall GetUserTokenFromSessionId(WUSystemInterfaceHelper *this, int *a2, _QWORD *a3)
{
  unsigned int v4; // edi
  int IsQueryUserTokenPresent; // ebx
  __int64 v6; // rdx
  unsigned __int64 v7; // r9
  int *v8; // r9
  int v9; // eax
  signed int v10; // edi
  __int64 v11; // rdx
  int v12; // eax
  signed int LastError; // eax
  HANDLE v14; // rcx
  HANDLE v15; // rax
  HANDLE hObject; // [rsp+20h] [rbp-20h] BYREF
  int v18; // [rsp+28h] [rbp-18h] BYREF
  void *v19; // [rsp+2Ch] [rbp-14h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+18h]

  hObject = 0;
  v4 = (unsigned int)this;
  if ( !a3 )
  {
    IsQueryUserTokenPresent = -2147467261;
    v6 = 251;
LABEL_7:
    v7 = (unsigned int)IsQueryUserTokenPresent;
LABEL_14:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v6,
      (unsigned int)"C:\\__w\\1\\s\\src\\Client\\lib\\util\\SecurityUtil.cpp",
      (const char *)v7,
      (int)hObject);
    goto LABEL_23;
  }
  v18 = 0;
  IsQueryUserTokenPresent = WUSystemInterfaceHelper::IsQueryUserTokenPresent((WUSystemInterfaceHelper *)&v18, a2);
  if ( IsQueryUserTokenPresent < 0 )
  {
    v6 = 254;
    goto LABEL_7;
  }
  if ( !v18 )
  {
    IsQueryUserTokenPresent = -2145124266;
    v6 = 255;
    goto LABEL_7;
  }
  if ( wil::details::FeatureImpl<__WilFeatureTraits_Feature_Containment_UUS_HandleNullUserToken_57723278>::__private_IsEnabled((__int64)`wil::Feature<__WilFeatureTraits_Feature_Containment_UUS_HandleNullUserToken_57723278>::GetImpl'::`2'::impl) )
  {
    v9 = QueryUserToken(v4, &hObject);
    v10 = v9;
    if ( v9 < 0 )
    {
      IsQueryUserTokenPresent = -2147023888;
      if ( v9 == -2147023888 )
      {
LABEL_23:
        v14 = hObject;
        goto LABEL_25;
      }
      v11 = 260;
LABEL_22:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v11,
        (unsigned int)"C:\\__w\\1\\s\\src\\Client\\lib\\util\\SecurityUtil.cpp",
        (const char *)(unsigned int)v10,
        (int)hObject);
      IsQueryUserTokenPresent = v10;
      goto LABEL_23;
    }
  }
  else
  {
    LODWORD(v19) = 0;
    v12 = WUSystemInterfaceHelper::QueryUserToken((WUSystemInterfaceHelper *)v4, (unsigned int)&hObject, &v19, v8);
    IsQueryUserTokenPresent = v12;
    if ( v12 < 0 )
    {
      v7 = (unsigned int)v12;
      v6 = 267;
      goto LABEL_14;
    }
    if ( !(_DWORD)v19 )
    {
      LastError = GetLastError();
      v10 = (unsigned __int16)LastError | 0x80070000;
      if ( LastError <= 0 )
        v10 = LastError;
      if ( v10 < 0 )
      {
        IsQueryUserTokenPresent = -2147023888;
        if ( v10 == -2147023888 )
          goto LABEL_23;
      }
      else
      {
        v10 = -2147418113;
      }
      v11 = 271;
      goto LABEL_22;
    }
  }
  v15 = hObject;
  v14 = 0;
  hObject = 0;
  IsQueryUserTokenPresent = 0;
  *a3 = v15;
LABEL_25:
  if ( v14 )
    CloseHandle(v14);
  return (unsigned int)IsQueryUserTokenPresent;
}

```

## disassembly

```asm
0x1400101e8  mov     [rsp-18h+arg_8], rbx
0x1400101ed  push    rbp
0x1400101ee  push    rsi
0x1400101ef  push    rdi
0x1400101f0  mov     rbp, rsp
0x1400101f3  sub     rsp, 40h
0x1400101f7  mov     rax, cs:__security_cookie
0x1400101fe  xor     rax, rsp
0x140010201  mov     [rbp+var_14+4], rax
0x140010205  mov     [rbp+hObject], 0
0x14001020d  mov     rsi, r8
0x140010210  mov     edi, ecx
0x140010212  test    r8, r8
0x140010215  jnz     short loc_140010223
0x140010217  mov     ebx, 80004003h
0x14001021c  mov     edx, 0FBh; int *
0x140010221  jmp     short loc_140010250
0x140010223  lea     rcx, [rbp+var_18]; this
0x140010227  mov     [rbp+var_18], 0
0x14001022e  call    ?IsQueryUserTokenPresent@WUSystemInterfaceHelper@@YAJPEAH@Z; WUSystemInterfaceHelper::IsQueryUserTokenPresent(int *)
0x140010233  mov     ebx, eax
0x140010235  test    eax, eax
0x140010237  jns     short loc_140010240
0x140010239  mov     edx, 0FEh
0x14001023e  jmp     short loc_140010250
0x140010240  cmp     [rbp+var_18], 0
0x140010244  jnz     short loc_140010255
0x140010246  mov     ebx, 80240056h
0x14001024b  mov     edx, 0FFh
0x140010250  mov     r9d, ebx
0x140010253  jmp     short loc_1400102CC
0x140010255  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Containment_UUS_HandleNullUserToken_57723278@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Containment_UUS_HandleNullUserToken_57723278@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Containment_UUS_HandleNullUserToken_57723278> `wil::Feature<__WilFeatureTraits_Feature_Containment_UUS_HandleNullUserToken_57723278>::GetImpl(void)'::`2'::impl
0x14001025c  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Containment_UUS_HandleNullUserToken_57723278@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Containment_UUS_HandleNullUserToken_57723278>::__private_IsEnabled(void)
0x140010261  mov     rcx, [rbp+hObject]; hObject
0x140010265  test    al, al
0x140010267  jz      short loc_14001029D
0x140010269  test    rcx, rcx
0x14001026c  jz      short loc_140010274
0x14001026e  call    cs:__imp_CloseHandle
0x140010274  lea     rdx, [rbp+hObject]
0x140010278  mov     ecx, edi
0x14001027a  call    QueryUserToken
0x14001027f  mov     edi, eax
0x140010281  test    eax, eax
0x140010283  jns     loc_14001032C
0x140010289  mov     ebx, 800703F0h
0x14001028e  cmp     eax, ebx
0x140010290  jz      loc_140010326
0x140010296  mov     edx, 104h
0x14001029b  jmp     short loc_140010311
0x14001029d  mov     dword ptr [rbp+var_14], 0
0x1400102a4  test    rcx, rcx
0x1400102a7  jz      short loc_1400102AF
0x1400102a9  call    cs:__imp_CloseHandle
0x1400102af  lea     r8, [rbp+var_14]; void **
0x1400102b3  mov     ecx, edi; this
0x1400102b5  lea     rdx, [rbp+hObject]; unsigned int
0x1400102b9  call    ?QueryUserToken@WUSystemInterfaceHelper@@YAJKPEAPEAXPEAH@Z; WUSystemInterfaceHelper::QueryUserToken(ulong,void * *,int *)
0x1400102be  mov     ebx, eax
0x1400102c0  test    eax, eax
0x1400102c2  jns     short loc_1400102DE
0x1400102c4  mov     r9d, eax; char *
0x1400102c7  mov     edx, 10Bh; void *
0x1400102cc  mov     rcx, [rbp+18h]; this
0x1400102d0  lea     r8, aCW1SSrcClientL_23; "C:\\__w\\1\\s\\src\\Client\\lib\\util\\"...
0x1400102d7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1400102dc  jmp     short loc_140010326
0x1400102de  cmp     dword ptr [rbp+var_14], 0
0x1400102e2  jnz     short loc_14001032C
0x1400102e4  call    cs:__imp_GetLastError
0x1400102ea  movzx   edi, ax
0x1400102ed  or      edi, 80070000h
0x1400102f3  test    eax, eax
0x1400102f5  cmovle  edi, eax
0x1400102f8  test    edi, edi
0x1400102fa  js      short loc_140010303
0x1400102fc  mov     edi, 8000FFFFh
0x140010301  jmp     short loc_14001030C
0x140010303  mov     ebx, 800703F0h
0x140010308  cmp     edi, ebx
0x14001030a  jz      short loc_140010326
0x14001030c  mov     edx, 10Fh; void *
0x140010311  mov     rcx, [rbp+18h]; this
0x140010315  lea     r8, aCW1SSrcClientL_23; "C:\\__w\\1\\s\\src\\Client\\lib\\util\\"...
0x14001031c  mov     r9d, edi; char *
0x14001031f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140010324  mov     ebx, edi
0x140010326  mov     rcx, [rbp+hObject]
0x14001032a  jmp     short loc_14001033B
0x14001032c  mov     rax, [rbp+hObject]
0x140010330  xor     ecx, ecx; hObject
0x140010332  mov     [rbp+hObject], rcx
0x140010336  xor     ebx, ebx
0x140010338  mov     [rsi], rax
0x14001033b  test    rcx, rcx
0x14001033e  jz      short loc_140010346
0x140010340  call    cs:__imp_CloseHandle
0x140010346  mov     eax, ebx
0x140010348  mov     rcx, [rbp+var_14+4]
0x14001034c  xor     rcx, rsp; StackCookie
0x14001034f  call    __security_check_cookie
0x140010354  mov     rbx, [rsp+40h+arg_8]
0x140010359  add     rsp, 40h
0x14001035d  pop     rdi
0x14001035e  pop     rsi
0x14001035f  pop     rbp
0x140010360  retn
```
