# CNgcNode::_CreateNode(_GUID const &,ushort const *,ushort const *,ushort const *,Microsoft::WRL::Wrappers::HandleT<ScDeviceEnum::SwDeviceHandleTraits> *,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> *)

- ea: `0x180012304`
- end: `0x180012908`
- name: `?_CreateNode@CNgcNode@@CAJAEBU_GUID@@PEBG11PEAV?$HandleT@USwDeviceHandleTraits@ScDeviceEnum@@@Wrappers@WRL@Microsoft@@PEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z`
- size: `1540`
- prototype: `__int64 __fastcall(GUID *rguid, __int64, _WORD *, __int64, __int64, __int64)`
- caller_count: `2`
- callee_count: `16`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180011ebc`
- `0x180012044`

## callees

- `0x180001610`
- `0x180006d40`
- `0x1800071d4`
- `0x180008608`
- `0x180008644`
- `0x180008af4`
- `0x180008bbc`
- `0x180009688`
- `0x180009840`
- `0x180009970`
- `0x1800119e0`
- `0x180011a88`
- `0x180011b2c`
- `0x180012304`
- `0x18001dfe2`
- `0x18001e020`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800123e5`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800123e5`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800127c3`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800127c3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800123fd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800127d4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800123fd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800127d4`
- `api-ms-win-devices-swdevice-l1-1-0!SwDeviceCreate` at `0x180012770`
- `api-ms-win-devices-swdevice-l1-1-0!SwDeviceCreate` at `0x180012770`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x180012486`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x180012486`

## string_xrefs

- `0x180012358`: `CNgcNode::_CreateNode`

## pseudocode

```c
__int64 __fastcall CNgcNode::_CreateNode(GUID *rguid, __int64 a2, _WORD *a3, __int64 a4, __int64 a5, __int64 a6)
{
  HANDLE EventW; // rax
  signed int LastError; // ebx
  __int64 v12; // rcx
  __int64 v13; // rcx
  unsigned int v14; // edx
  __int64 v15; // rcx
  __int64 v16; // rcx
  __int64 v17; // rsi
  __int64 v18; // rax
  int v19; // eax
  int v20; // edx
  __int64 v21; // r8
  __int64 v22; // rbx
  _QWORD *v23; // rcx
  _QWORD *v24; // rcx
  _QWORD *v25; // r8
  __int64 v26; // rdx
  __int64 *v27; // rdx
  __int64 v28; // rcx
  _QWORD *v29; // rcx
  int v30; // edx
  DWORD v31; // eax
  __int64 v32; // rcx
  __int64 v33; // rdx
  int v35; // [rsp+40h] [rbp-C0h] BYREF
  const unsigned __int16 *v36; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v37; // [rsp+50h] [rbp-B0h] BYREF
  int v38; // [rsp+58h] [rbp-A8h] BYREF
  _QWORD *v39; // [rsp+60h] [rbp-A0h] BYREF
  _QWORD v40[3]; // [rsp+68h] [rbp-98h] BYREF
  int v41; // [rsp+80h] [rbp-80h] BYREF
  OLECHAR *v42; // [rsp+88h] [rbp-78h]
  const wchar_t *v43; // [rsp+90h] [rbp-70h]
  int v44; // [rsp+A8h] [rbp-58h]
  const wchar_t *v45; // [rsp+B0h] [rbp-50h]
  _QWORD v46[2]; // [rsp+D0h] [rbp-30h] BYREF
  __int64 v47; // [rsp+E0h] [rbp-20h]
  unsigned __int64 v48; // [rsp+E8h] [rbp-18h]
  void **v49; // [rsp+F0h] [rbp-10h] BYREF
  HANDLE hHandle; // [rsp+F8h] [rbp-8h]
  __int64 v51; // [rsp+100h] [rbp+0h]
  _WORD v52[8]; // [rsp+108h] [rbp+8h] BYREF
  __int64 v53; // [rsp+118h] [rbp+18h]
  __int64 v54; // [rsp+120h] [rbp+20h]
  __int128 v55; // [rsp+130h] [rbp+30h] BYREF
  int v56; // [rsp+140h] [rbp+40h]
  _DWORD v57[3]; // [rsp+144h] [rbp+44h]
  int v58; // [rsp+150h] [rbp+50h]
  int v59; // [rsp+154h] [rbp+54h]
  __int64 v60; // [rsp+158h] [rbp+58h]
  DEVPROPKEY v61; // [rsp+160h] [rbp+60h]
  int v62; // [rsp+174h] [rbp+74h]
  int v63; // [rsp+180h] [rbp+80h]
  int v64; // [rsp+184h] [rbp+84h]
  __int64 v65; // [rsp+188h] [rbp+88h]
  char v66[32]; // [rsp+1F0h] [rbp+F0h] BYREF
  OLECHAR sz[40]; // [rsp+210h] [rbp+110h] BYREF

  v35 = 0;
  v38 = 0;
  strcpy(v66, "CNgcNode::_CreateNode");
  v40[0] = v66;
  v40[1] = &v38;
  v40[2] = &v35;
  lambda_7be7afca1423402b1f1865db2c4c8511_::operator()(v40);
  v38 = 1;
  v39 = v40;
  hHandle = 0;
  v49 = &Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::HANDLENullTraits>::`vftable';
  v54 = 7;
  v53 = 0;
  v52[0] = 0;
  v51 = 0;
  EventW = CreateEventW(0, 1, 0, 0);
  Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::EventTraits>::Attach(&v49, EventW);
  if ( !hHandle )
  {
    LastError = GetLastError();
    WppTraceIndent(v12, 2);
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_sd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        15,
        (unsigned int)&WPP_b74ae1c4b2e3343dbdeda7c30d77c9e0_Traceguids,
        (_DWORD)WPP_pszIndent,
        LastError);
    }
    if ( LastError > 0 )
      LastError = (unsigned __int16)LastError | 0x80070000;
    v35 = LastError;
    goto LABEL_66;
  }
  memset_0(sz, 0, 0x4Eu);
  if ( StringFromGUID2(rguid, sz, 39) )
  {
    memset_0(&v41, 0, 0x48u);
    v41 = 72;
    v42 = sz;
    v43 = L"NgcDeviceEnum\\node";
    v45 = L"NGC Container Node";
    v44 = 6;
    memset_0(&v55, 0, 0xC0u);
    v14 = 0;
    if ( a2 )
    {
      v15 = -1;
      do
        ++v15;
      while ( *(_WORD *)(a2 + 2 * v15) );
      v55 = DEVPKEY_Device_NgcContainerName;
      v56 = 3;
      v57[0] = 0;
      v58 = 18;
      v59 = 2 * v15 + 2;
      v60 = a2;
      v14 = 2;
      v61 = DEVPKEY_Device_FriendlyName;
      v62 = 0;
      v63 = 18;
      v64 = v59;
      v65 = a2;
    }
    v16 = 6LL * v14;
    v17 = v14 + 1;
    if ( a4 )
    {
      v18 = -1;
      do
        ++v18;
      while ( *(_WORD *)(a4 + 2 * v18) );
      *(&v55 + 3 * v14) = DEVPKEY_Device_NgcOwnerSid;
      v57[12 * v14 - 1] = 4;
      v19 = 2 * v18 + 2;
      v20 = 18;
    }
    else
    {
      *(&v55 + 3 * v14) = DEVPKEY_Device_NgcOwnerSid;
      v57[12 * v14 - 1] = 4;
      a4 = 0;
      v19 = 0;
      v20 = 0;
    }
    v57[2 * v16] = 0;
    *(&v58 + 2 * v16) = v20;
    *(&v59 + 2 * v16) = v19;
    *(&v60 + v16) = a4;
    v48 = 7;
    v47 = 0;
    LOWORD(v46[0]) = 0;
    if ( a3 )
    {
      if ( *a3 )
      {
        v21 = -1;
        do
          ++v21;
        while ( a3[v21] );
      }
      else
      {
        v21 = 0;
      }
      std::wstring::assign(v46, a3, v21);
      if ( v47 == -1 || v47 == -2 )
        std::_Xlength_error("string too long");
      v22 = v47 + 1;
      if ( (unsigned __int8)std::wstring::_Grow(v46, v47 + 1) )
      {
        v23 = v46;
        if ( v48 >= 8 )
          v23 = (_QWORD *)v46[0];
        *((_WORD *)v23 + v47) = 0;
        v24 = v46;
        if ( v48 >= 8 )
          v24 = (_QWORD *)v46[0];
        v47 = v22;
        *((_WORD *)v24 + v22) = 0;
      }
      v25 = v46;
      if ( v48 >= 8 )
        v25 = (_QWORD *)v46[0];
      v26 = 6 * v17;
      LODWORD(v17) = v17 + 1;
      *(__int128 *)((char *)&v55 + 8 * v26) = (__int128)DEVPKEY_DrvPkg_Icon.fmtid;
      v57[2 * v26 - 1] = DEVPKEY_DrvPkg_Icon.pid;
      v57[2 * v26] = 0;
      *(&v58 + 2 * v26) = 8210;
      *(&v59 + 2 * v26) = 2 * v47 + 2;
      *(&v60 + v26) = (__int64)v25;
    }
    v36 = &Microsoft::WRL::Wrappers::HandleT<ScDeviceEnum::SwDeviceHandleTraits>::`vftable';
    v37 = 0;
    Microsoft::WRL::Wrappers::HandleT<ScDeviceEnum::SwDeviceHandleTraits>::Close(&v36);
    v27 = &qword_18002B100;
    if ( (unsigned __int64)qword_18002B118 >= 8 )
      v27 = (__int64 *)qword_18002B100;
    v35 = SwDeviceCreate(
            L"NgcDeviceEnum",
            v27,
            &v41,
            (unsigned int)v17,
            &v55,
            CNgcNode::_DeviceCreateCallback,
            &v49,
            &v37);
    if ( v35 >= 0 )
    {
      v31 = WaitForSingleObject(hHandle, 0x2710u);
      LastError = v31;
      if ( v31 )
      {
        if ( v31 == -1 )
          LastError = GetLastError();
        WppTraceIndent(v32, 2);
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_sd(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            18,
            (unsigned int)&WPP_b74ae1c4b2e3343dbdeda7c30d77c9e0_Traceguids,
            (_DWORD)WPP_pszIndent,
            LastError);
        }
        if ( LastError > 0 )
          LastError = (unsigned __int16)LastError | 0x80070000;
        v35 = LastError;
        goto LABEL_65;
      }
      if ( (int)v51 >= 0 )
      {
        std::wstring::operator=(a6, v52);
        Microsoft::WRL::Wrappers::HandleT<ScDeviceEnum::SwDeviceHandleTraits>::operator=(a5, &v36);
        goto LABEL_64;
      }
      v35 = v51;
      WppTraceIndent(v32, 2);
      v29 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_64;
      }
      v30 = 19;
    }
    else
    {
      WppTraceIndent(v28, 2);
      v29 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_64;
      }
      v30 = 17;
    }
    WPP_SF_sd(v29[2], v30, (unsigned int)&WPP_b74ae1c4b2e3343dbdeda7c30d77c9e0_Traceguids, (_DWORD)WPP_pszIndent, v35);
LABEL_64:
    LastError = v35;
LABEL_65:
    v36 = &Microsoft::WRL::Wrappers::HandleT<ScDeviceEnum::SwDeviceHandleTraits>::`vftable';
    Microsoft::WRL::Wrappers::HandleT<ScDeviceEnum::SwDeviceHandleTraits>::Close(&v36);
    LOBYTE(v33) = 1;
    std::wstring::_Tidy(v46, v33, 0);
    goto LABEL_66;
  }
  v35 = -2147024774;
  WppTraceIndent(v13, 2);
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    WPP_SF_sd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      16,
      (unsigned int)&WPP_b74ae1c4b2e3343dbdeda7c30d77c9e0_Traceguids,
      (_DWORD)WPP_pszIndent,
      v35);
  }
  LastError = v35;
LABEL_66:
  CNgcNode::CDeviceCreateContext::~CDeviceCreateContext((CNgcNode::CDeviceCreateContext *)&v49);
  WppTraceUnwinder__lambda_7be7afca1423402b1f1865db2c4c8511____::_WppTraceUnwinder__lambda_7be7afca1423402b1f1865db2c4c8511____(&v39);
  return (unsigned int)LastError;
}

```

## disassembly

```asm
0x180012304  mov     [rsp-8+arg_8], rbx
0x180012309  push    rbp
0x18001230a  push    rsi
0x18001230b  push    rdi
0x18001230c  push    r12
0x18001230e  push    r13
0x180012310  push    r14
0x180012312  push    r15
0x180012314  lea     rbp, [rsp-170h]
0x18001231c  sub     rsp, 270h
0x180012323  mov     rax, cs:__security_cookie
0x18001232a  xor     rax, rsp
0x18001232d  mov     [rbp+1A0h+var_40], rax
0x180012334  mov     r15, r9
0x180012337  mov     r14, r8
0x18001233a  mov     rsi, rdx
0x18001233d  mov     rbx, rcx
0x180012340  mov     r12, [rbp+1A0h+arg_20]
0x180012347  mov     r13, [rbp+1A0h+arg_28]
0x18001234e  xor     edi, edi
0x180012350  mov     [rsp+2A0h+var_260], edi
0x180012354  mov     [rsp+2A0h+var_248], edi
0x180012358  movups  xmm0, xmmword ptr cs:aCngcnodeCreate_0; "CNgcNode::_CreateNode"
0x18001235f  movups  xmmword ptr [rbp+1A0h+var_B0], xmm0
0x180012366  movsd   xmm1, qword ptr cs:aCngcnodeCreate_0+0Eh; "ateNode"
0x18001236e  movsd   qword ptr [rbp+1A0h+var_B0+0Eh], xmm1
0x180012376  lea     rax, [rbp+1A0h+var_B0]
0x18001237d  mov     [rsp+2A0h+var_238], rax
0x180012382  lea     rax, [rsp+2A0h+var_248]
0x180012387  mov     [rsp+2A0h+var_230], rax
0x18001238c  lea     rax, [rsp+2A0h+var_260]
0x180012391  mov     [rsp+2A0h+var_228], rax
0x180012396  lea     rcx, [rsp+2A0h+var_238]
0x18001239b  call    _lambda_7be7afca1423402b1f1865db2c4c8511___operator__
0x1800123a0  mov     [rsp+2A0h+var_248], 1
0x1800123a8  lea     rax, [rsp+2A0h+var_238]
0x1800123ad  mov     [rsp+2A0h+var_240], rax
0x1800123b2  mov     [rbp+1A0h+hHandle], rdi
0x1800123b6  lea     rax, ??_7?$HandleT@UHANDLENullTraits@HandleTraits@Wrappers@WRL@Microsoft@@@Wrappers@WRL@Microsoft@@6B@; const Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::HANDLENullTraits>::`vftable'
0x1800123bd  mov     [rbp+1A0h+var_1B0], rax
0x1800123c1  xor     eax, eax
0x1800123c3  mov     [rbp+1A0h+var_1A0], rax
0x1800123c7  mov     [rbp+1A0h+var_180], 7
0x1800123cf  mov     [rbp+1A0h+var_188], rdi
0x1800123d3  mov     [rbp+1A0h+var_198], di
0x1800123d7  mov     dword ptr [rbp+1A0h+var_1A0], edi
0x1800123da  xor     r9d, r9d; lpName
0x1800123dd  xor     r8d, r8d; bInitialState
0x1800123e0  lea     edx, [rdi+1]; bManualReset
0x1800123e3  xor     ecx, ecx; lpEventAttributes
0x1800123e5  call    cs:__imp_CreateEventW
0x1800123eb  mov     rdx, rax
0x1800123ee  lea     rcx, [rbp+1A0h+var_1B0]
0x1800123f2  call    ?Attach@?$HandleT@UEventTraits@HandleTraits@Wrappers@WRL@Microsoft@@@Wrappers@WRL@Microsoft@@QEAAXPEAX@Z; Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::EventTraits>::Attach(void *)
0x1800123f7  cmp     [rbp+1A0h+hHandle], rdi
0x1800123fb  jnz     short loc_180012464
0x1800123fd  call    cs:__imp_GetLastError
0x180012403  mov     ebx, eax
0x180012405  mov     edi, 2
0x18001240a  mov     edx, edi
0x18001240c  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x180012411  lea     rax, WPP_GLOBAL_Control
0x180012418  mov     rcx, cs:WPP_GLOBAL_Control
0x18001241f  cmp     rcx, rax
0x180012422  jz      short loc_18001244E
0x180012424  test    byte ptr [rcx+1Ch], 1
0x180012428  jz      short loc_18001244E
0x18001242a  cmp     [rcx+19h], dil
0x18001242e  jb      short loc_18001244E
0x180012430  lea     edx, [rdi+0Dh]
0x180012433  mov     dword ptr [rsp+2A0h+var_280], ebx
0x180012437  mov     r9, cs:?WPP_pszIndent@@3PEADEA; char * WPP_pszIndent
0x18001243e  lea     r8, WPP_b74ae1c4b2e3343dbdeda7c30d77c9e0_Traceguids
0x180012445  mov     rcx, [rcx+10h]
0x180012449  call    WPP_SF_sd
0x18001244e  test    ebx, ebx
0x180012450  jle     short loc_18001245B
0x180012452  movzx   ebx, bx
0x180012455  or      ebx, 80070000h
0x18001245b  mov     [rsp+2A0h+var_260], ebx
0x18001245f  jmp     loc_1800128C8
0x180012464  xor     edx, edx; Val
0x180012466  lea     r8d, [rdx+4Eh]; Size
0x18001246a  lea     rcx, [rbp+1A0h+sz]; void *
0x180012471  call    memset_0
0x180012476  mov     r8d, 27h ; '''; cchMax
0x18001247c  lea     rdx, [rbp+1A0h+sz]; lpsz
0x180012483  mov     rcx, rbx; rguid
0x180012486  call    cs:__imp_StringFromGUID2
0x18001248c  test    eax, eax
0x18001248e  jnz     short loc_1800124EC
0x180012490  mov     [rsp+2A0h+var_260], 8007007Ah
0x180012498  lea     edi, [rax+2]
0x18001249b  mov     edx, edi
0x18001249d  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x1800124a2  lea     rax, WPP_GLOBAL_Control
0x1800124a9  mov     rcx, cs:WPP_GLOBAL_Control
0x1800124b0  cmp     rcx, rax
0x1800124b3  jz      short loc_1800124E3
0x1800124b5  test    byte ptr [rcx+1Ch], 1
0x1800124b9  jz      short loc_1800124E3
0x1800124bb  cmp     [rcx+19h], dil
0x1800124bf  jb      short loc_1800124E3
0x1800124c1  lea     edx, [rdi+0Eh]
0x1800124c4  mov     eax, [rsp+2A0h+var_260]
0x1800124c8  mov     dword ptr [rsp+2A0h+var_280], eax
0x1800124cc  mov     r9, cs:?WPP_pszIndent@@3PEADEA; char * WPP_pszIndent
0x1800124d3  lea     r8, WPP_b74ae1c4b2e3343dbdeda7c30d77c9e0_Traceguids
0x1800124da  mov     rcx, [rcx+10h]
0x1800124de  call    WPP_SF_sd
0x1800124e3  mov     ebx, [rsp+2A0h+var_260]
0x1800124e7  jmp     loc_1800128C8
0x1800124ec  mov     ebx, 48h ; 'H'
0x1800124f1  mov     r8d, ebx; Size
0x1800124f4  xor     edx, edx; Val
0x1800124f6  lea     rcx, [rbp+1A0h+var_220]; void *
0x1800124fa  call    memset_0
0x1800124ff  mov     [rbp+1A0h+var_220], ebx
0x180012502  lea     rax, [rbp+1A0h+sz]
0x180012509  mov     [rbp+1A0h+var_218], rax
0x18001250d  lea     rax, aNgcdeviceenumN; "NgcDeviceEnum\\node"
0x180012514  mov     [rbp+1A0h+var_210], rax
0x180012518  lea     rax, aNgcContainerNo; "NGC Container Node"
0x18001251f  mov     [rbp+1A0h+var_1F0], rax
0x180012523  mov     [rbp+1A0h+var_1F8], 6
0x18001252a  xor     edx, edx; Val
0x18001252c  lea     r8d, [rbx+78h]; Size
0x180012530  lea     rcx, [rbp+1A0h+var_170]; void *
0x180012534  call    memset_0
0x180012539  xor     r9d, r9d
0x18001253c  mov     edx, r9d
0x18001253f  lea     edi, [rbx-46h]
0x180012542  or      rbx, 0FFFFFFFFFFFFFFFFh
0x180012546  lea     r8d, [r9+12h]
0x18001254a  test    rsi, rsi
0x18001254d  jz      short loc_1800125B4
0x18001254f  movups  xmm0, cs:DEVPKEY_Device_NgcContainerName
0x180012556  mov     eax, cs:dword_180024700
0x18001255c  mov     rcx, rbx
0x18001255f  inc     rcx
0x180012562  cmp     [rsi+rcx*2], r9w
0x180012567  jnz     short loc_18001255F
0x180012569  lea     ecx, ds:2[rcx*2]
0x180012570  movaps  [rbp+1A0h+var_170], xmm0
0x180012574  mov     [rbp+1A0h+var_160], eax
0x180012577  mov     [rbp+1A0h+var_15C], r9d
0x18001257b  mov     [rbp+1A0h+var_150], r8d
0x18001257f  mov     [rbp+1A0h+var_14C], ecx
0x180012582  mov     [rbp+1A0h+var_148], rsi
0x180012586  mov     edx, edi
0x180012588  movups  xmm0, xmmword ptr cs:DEVPKEY_Device_FriendlyName.fmtid.Data1
0x18001258f  movaps  [rbp+1A0h+var_140], xmm0
0x180012593  mov     eax, cs:DEVPKEY_Device_FriendlyName.pid
0x180012599  mov     [rbp+1A0h+var_130], eax
0x18001259c  mov     [rbp+1A0h+var_12C], r9d
0x1800125a0  mov     [rbp+1A0h+var_120], r8d
0x1800125a7  mov     [rbp+1A0h+var_11C], ecx
0x1800125ad  mov     [rbp+1A0h+var_118], rsi
0x1800125b4  mov     eax, edx
0x1800125b6  lea     rcx, [rax+rax*2]
0x1800125ba  add     rcx, rcx
0x1800125bd  lea     esi, [rdx+1]
0x1800125c0  movups  xmm0, cs:DEVPKEY_Device_NgcOwnerSid
0x1800125c7  test    r15, r15
0x1800125ca  jz      short loc_1800125F4
0x1800125cc  mov     edx, cs:dword_1800246E8
0x1800125d2  mov     rax, rbx
0x1800125d5  inc     rax
0x1800125d8  cmp     [r15+rax*2], r9w
0x1800125dd  jnz     short loc_1800125D5
0x1800125df  movups  [rbp+rcx*8+1A0h+var_170], xmm0
0x1800125e4  mov     [rbp+rcx*8+1A0h+var_160], edx
0x1800125e8  lea     eax, ds:2[rax*2]
0x1800125ef  mov     edx, r8d
0x1800125f2  jmp     short loc_18001260C
0x1800125f4  movups  [rbp+rcx*8+1A0h+var_170], xmm0
0x1800125f9  mov     eax, cs:dword_1800246E8
0x1800125ff  mov     [rbp+rcx*8+1A0h+var_160], eax
0x180012603  mov     r15, r9
0x180012606  mov     eax, r9d
0x180012609  mov     edx, r9d
0x18001260c  mov     [rbp+rcx*8+1A0h+var_15C], r9d
0x180012611  mov     [rbp+rcx*8+1A0h+var_150], edx
0x180012615  mov     [rbp+rcx*8+1A0h+var_14C], eax
0x180012619  mov     [rbp+rcx*8+1A0h+var_148], r15
0x18001261e  mov     [rbp+1A0h+var_1B8], 7
0x180012626  mov     [rbp+1A0h+var_1C0], r9
0x18001262a  mov     word ptr [rbp+1A0h+var_1D0], r9w
0x18001262f  test    r14, r14
0x180012632  jz      loc_180012708
0x180012638  cmp     [r14], r9w
0x18001263c  jnz     short loc_180012643
0x18001263e  mov     r8, r9
0x180012641  jmp     short loc_180012650
0x180012643  mov     r8, rbx
0x180012646  inc     r8
0x180012649  cmp     [r14+r8*2], r9w
0x18001264e  jnz     short loc_180012646
0x180012650  mov     rdx, r14
0x180012653  lea     rcx, [rbp+1A0h+var_1D0]
0x180012657  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG_K@Z; std::wstring::assign(ushort const *,unsigned __int64)
0x18001265c  mov     rax, [rbp+1A0h+var_1C0]
0x180012660  sub     rbx, rax
0x180012663  cmp     rbx, 1
0x180012667  ja      short loc_180012676
0x180012669  lea     rcx, aStringTooLong; "string too long"
0x180012670  call    ?_Xlength_error@std@@YAXPEBD@Z; std::_Xlength_error(char const *)
0x180012676  lea     rbx, [rax+1]
0x18001267a  mov     rdx, rbx
0x18001267d  lea     rcx, [rbp+1A0h+var_1D0]
0x180012681  call    ?_Grow@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA_N_K_N@Z; std::wstring::_Grow(unsigned __int64,bool)
0x180012686  xor     r9d, r9d
0x180012689  test    al, al
0x18001268b  jz      short loc_1800126BB
0x18001268d  mov     rdx, [rbp+1A0h+var_1C0]
0x180012691  lea     rcx, [rbp+1A0h+var_1D0]
0x180012695  cmp     [rbp+1A0h+var_1B8], 8
0x18001269a  cmovnb  rcx, [rbp+1A0h+var_1D0]
0x18001269f  mov     [rcx+rdx*2], r9w
0x1800126a4  lea     rcx, [rbp+1A0h+var_1D0]
0x1800126a8  cmp     [rbp+1A0h+var_1B8], 8
0x1800126ad  cmovnb  rcx, [rbp+1A0h+var_1D0]
0x1800126b2  mov     [rbp+1A0h+var_1C0], rbx
0x1800126b6  mov     [rcx+rbx*2], r9w
0x1800126bb  lea     r8, [rbp+1A0h+var_1D0]
0x1800126bf  cmp     [rbp+1A0h+var_1B8], 8
0x1800126c4  cmovnb  r8, [rbp+1A0h+var_1D0]
0x1800126c9  movups  xmm0, xmmword ptr cs:DEVPKEY_DrvPkg_Icon.fmtid.Data1
0x1800126d0  mov     ecx, cs:DEVPKEY_DrvPkg_Icon.pid
0x1800126d6  lea     rdx, [rsi+rsi*2]
0x1800126da  add     rdx, rdx
0x1800126dd  inc     esi
0x1800126df  movups  [rbp+rdx*8+1A0h+var_170], xmm0
0x1800126e4  mov     [rbp+rdx*8+1A0h+var_160], ecx
0x1800126e8  mov     [rbp+rdx*8+1A0h+var_15C], r9d
0x1800126ed  mov     [rbp+rdx*8+1A0h+var_150], 2012h
0x1800126f5  mov     eax, dword ptr [rbp+1A0h+var_1C0]
0x1800126f8  lea     eax, ds:2[rax*2]
0x1800126ff  mov     [rbp+rdx*8+1A0h+var_14C], eax
0x180012703  mov     [rbp+rdx*8+1A0h+var_148], r8
0x180012708  lea     r14, ??_7?$HandleT@USwDeviceHandleTraits@ScDeviceEnum@@@Wrappers@WRL@Microsoft@@6B@; const Microsoft::WRL::Wrappers::HandleT<ScDeviceEnum::SwDeviceHandleTraits>::`vftable'
0x18001270f  mov     [rsp+2A0h+var_258], r14
0x180012714  mov     [rsp+2A0h+var_250], r9
0x180012719  lea     rcx, [rsp+2A0h+var_258]
0x18001271e  call    ?Close@?$HandleT@USwDeviceHandleTraits@ScDeviceEnum@@@Wrappers@WRL@Microsoft@@QEAAXXZ; Microsoft::WRL::Wrappers::HandleT<ScDeviceEnum::SwDeviceHandleTraits>::Close(void)
0x180012723  lea     rdx, qword_18002B100
0x18001272a  cmp     cs:qword_18002B118, 8
0x180012732  cmovnb  rdx, cs:qword_18002B100
0x18001273a  lea     rax, [rsp+2A0h+var_250]
0x18001273f  mov     [rsp+2A0h+var_268], rax
0x180012744  lea     rax, [rbp+1A0h+var_1B0]
0x180012748  mov     [rsp+2A0h+var_270], rax
0x18001274d  lea     rax, ?_DeviceCreateCallback@CNgcNode@@CAXPEAUHSWDEVICE__@@JPEAXPEBG@Z; CNgcNode::_DeviceCreateCallback(HSWDEVICE__ *,long,void *,ushort const *)
0x180012754  mov     [rsp+2A0h+var_278], rax
0x180012759  lea     rax, [rbp+1A0h+var_170]
0x18001275d  mov     [rsp+2A0h+var_280], rax
0x180012762  mov     r9d, esi
0x180012765  lea     r8, [rbp+1A0h+var_220]
0x180012769  lea     rcx, aNgcdeviceenum; "NgcDeviceEnum"
0x180012770  call    cs:__imp_SwDeviceCreate
0x180012776  mov     [rsp+2A0h+var_260], eax
0x18001277a  test    eax, eax
0x18001277c  jns     short loc_1800127BA
0x18001277e  mov     edx, edi
0x180012780  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x180012785  lea     rax, WPP_GLOBAL_Control
0x18001278c  mov     rcx, cs:WPP_GLOBAL_Control
0x180012793  cmp     rcx, rax
0x180012796  jz      loc_1800128A5
0x18001279c  test    byte ptr [rcx+1Ch], 1
0x1800127a0  jz      loc_1800128A5
0x1800127a6  cmp     [rcx+19h], dil
0x1800127aa  jb      loc_1800128A5
0x1800127b0  mov     edx, 11h
0x1800127b5  jmp     loc_18001286B
0x1800127ba  mov     edx, 2710h; dwMilliseconds
0x1800127bf  mov     rcx, [rbp+1A0h+hHandle]; hHandle
0x1800127c3  call    cs:__imp_WaitForSingleObject
0x1800127c9  mov     ebx, eax
0x1800127cb  test    eax, eax
0x1800127cd  jz      short loc_180012835
0x1800127cf  cmp     eax, 0FFFFFFFFh
0x1800127d2  jnz     short loc_1800127DC
0x1800127d4  call    cs:__imp_GetLastError
0x1800127da  mov     ebx, eax
0x1800127dc  mov     edx, edi
0x1800127de  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x1800127e3  lea     rax, WPP_GLOBAL_Control
0x1800127ea  mov     rcx, cs:WPP_GLOBAL_Control
0x1800127f1  cmp     rcx, rax
0x1800127f4  jz      short loc_180012822
0x1800127f6  test    byte ptr [rcx+1Ch], 1
0x1800127fa  jz      short loc_180012822
0x1800127fc  cmp     [rcx+19h], dil
0x180012800  jb      short loc_180012822
0x180012802  mov     edx, 12h
0x180012807  mov     dword ptr [rsp+2A0h+var_280], ebx
0x18001280b  mov     r9, cs:?WPP_pszIndent@@3PEADEA; char * WPP_pszIndent
0x180012812  lea     r8, WPP_b74ae1c4b2e3343dbdeda7c30d77c9e0_Traceguids
0x180012819  mov     rcx, [rcx+10h]
  ... truncated ...
```
