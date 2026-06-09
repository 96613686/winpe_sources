# Microsoft::Bluetooth::Services::BthServ::BthpFindAndStampPnpInfoFromServiceSearch(_BLUETOOTH_DEVICE_INFO const *)

- ea: `0x180024004`
- end: `0x18002472f`
- name: `?BthpFindAndStampPnpInfoFromServiceSearch@BthServ@Services@Bluetooth@Microsoft@@YAJPEBU_BLUETOOTH_DEVICE_INFO@@@Z`
- size: `1835`
- prototype: `__int64 __fastcall(Microsoft::Bluetooth::Services::BthServ *__hidden this, const struct _BLUETOOTH_DEVICE_INFO *)`
- caller_count: `1`
- callee_count: `13`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x1800237e8`

## callees

- `0x180001790`
- `0x1800024ac`
- `0x180007bc4`
- `0x180007be4`
- `0x1800110fc`
- `0x180022688`
- `0x180024004`
- `0x180028430`
- `0x180028450`
- `0x180028468`
- `0x180035138`
- `0x180035bbc`
- `0x180036170`

## import_xrefs

- `ntdll!RtlNtStatusToDosError` at `0x180024262`
- `ntdll!RtlNtStatusToDosError` at `0x18002434b`
- `ntdll!RtlNtStatusToDosError` at `0x180024262`
- `ntdll!RtlNtStatusToDosError` at `0x18002434b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800240ce`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800246a1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800246bc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800246d3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800246ea`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180024701`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180024718`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800240ce`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800246a1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800246bc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800246d3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800246ea`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180024701`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180024718`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800240e1`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800240e1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800240d9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180024119`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180024490`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180024676`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800240d9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180024119`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180024490`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180024676`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x180024166`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x1800241ed`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x1800242f5`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x180024416`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x18002447a`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x180024515`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x180024660`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x180024166`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x1800241ed`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x1800242f5`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x180024416`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x18002447a`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x180024515`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x180024660`

## pseudocode

```c
__int64 __fastcall Microsoft::Bluetooth::Services::BthServ::BthpFindAndStampPnpInfoFromServiceSearch(
        Microsoft::Bluetooth::Services::BthServ *this,
        const struct _BLUETOOTH_DEVICE_INFO *a2)
{
  void *v3; // rcx
  char v4; // dl
  signed int v5; // edi
  void *v6; // r15
  HANDLE *v7; // rsi
  HANDLE v8; // r14
  DWORD LastError; // ebx
  HANDLE v10; // rcx
  bool v11; // cc
  const char *v13; // r9
  NTSTATUS v14; // eax
  signed int v15; // eax
  int *v16; // rsi
  NTSTATUS AttributeInTree; // eax
  signed int v18; // eax
  const char *v19; // r9
  unsigned int v20; // ebx
  __int64 v21; // rdx
  signed int v22; // eax
  int v23; // edx
  unsigned int v24; // r8d
  signed int v25; // eax
  int v26; // edx
  unsigned int v27; // r8d
  signed int v28; // eax
  int v29; // edx
  unsigned int v30; // r8d
  signed int v31; // eax
  int v32; // edx
  unsigned int v33; // r8d
  signed int v34; // eax
  int v35; // edx
  unsigned int v36; // r8d
  signed int v37; // eax
  int v38; // edx
  unsigned int v39; // r8d
  int lpOutBuffer; // [rsp+20h] [rbp-E0h]
  int lpOutBuffera; // [rsp+20h] [rbp-E0h]
  const char *nOutBufferSize; // [rsp+28h] [rbp-D8h]
  HANDLE hObject; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v44; // [rsp+58h] [rbp-A8h] BYREF
  void **v45; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v46; // [rsp+68h] [rbp-98h] BYREF
  int v47; // [rsp+70h] [rbp-90h] BYREF
  __int16 v48; // [rsp+74h] [rbp-8Ch]
  char v49; // [rsp+76h] [rbp-8Ah] BYREF
  int v50; // [rsp+78h] [rbp-88h] BYREF
  _DWORD InBuffer[5]; // [rsp+80h] [rbp-80h] BYREF
  char v52; // [rsp+94h] [rbp-6Ch]
  __int64 v53; // [rsp+98h] [rbp-68h] BYREF
  HANDLE *p_hObject; // [rsp+A0h] [rbp-60h]
  void *v55; // [rsp+A8h] [rbp-58h] BYREF
  char v56; // [rsp+B0h] [rbp-50h]
  __int64 v57; // [rsp+C0h] [rbp-40h] BYREF
  __int16 v58; // [rsp+CCh] [rbp-34h]
  __int16 v59; // [rsp+DCh] [rbp-24h]
  int v60; // [rsp+1BCh] [rbp+BCh]
  __int64 v61; // [rsp+1C0h] [rbp+C0h] BYREF
  int v62; // [rsp+1CCh] [rbp+CCh]
  __int16 v63; // [rsp+1D0h] [rbp+D0h]
  __int16 v64; // [rsp+1D2h] [rbp+D2h]
  __int16 v65; // [rsp+1D6h] [rbp+D6h]
  _BYTE OutBuffer[4]; // [rsp+8F0h] [rbp+7F0h] BYREF
  int v67; // [rsp+8F4h] [rbp+7F4h]
  char v68; // [rsp+8F8h] [rbp+7F8h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+A28h] [rbp+928h]

  v3 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (v4 = 1, *((_BYTE *)WPP_GLOBAL_Control + 25) < 5u) )
    v4 = 0;
  if ( v4 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    WPP_RECORDER_AND_TRACE_SF_s(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v4,
      WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED,
      *((_QWORD *)WPP_GLOBAL_Control + 5));
  hObject = 0;
  p_hObject = &hObject;
  v55 = 0;
  v56 = 1;
  v5 = BthDevnodeOpenInterfaceHandle(v3, 0, &v55);
  if ( v56 )
  {
    v6 = v55;
    v7 = p_hObject;
    v8 = *p_hObject;
    if ( (char *)*p_hObject - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
    {
      LastError = GetLastError();
      CloseHandle(v8);
      SetLastError(LastError);
    }
    *v7 = v6;
  }
  if ( v5 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xC7,
      (unsigned int)"onecore\\drivers\\wdm\\bluetooth\\user\\bthserv\\server\\bluetoothapis\\lib\\bthservbthapis.cpp",
      (const char *)(unsigned int)v5,
      lpOutBuffer);
    goto LABEL_13;
  }
  memset(&InBuffer[2], 0, 12);
  *(_QWORD *)InBuffer = *((_QWORD *)this + 1);
  v52 = 10;
  if ( DeviceIoControl(hObject, 0x410200u, InBuffer, 0x15u, InBuffer, 0x15u, 0, 0) )
  {
    memset_0(&v57, 0, 0x100u);
    v57 = *(_QWORD *)&InBuffer[3];
    v58 = 4608;
    v59 = 304;
    v60 = 33882625;
    memset_0(OutBuffer, 0, 0xD1u);
    if ( DeviceIoControl(hObject, 0x410210u, &v57, 0x100u, OutBuffer, 0xD1u, 0, 0) )
    {
      v45 = &Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::SdpTreeTraits>::`vftable';
      v46 = 0;
      v44 = 0;
      v53 = 0;
      v50 = 0;
      SdpGetNextElement((unsigned int)&v68, v67, 0, (unsigned int)&v53, (__int64)&v50);
      if ( v53 && v50 )
      {
        v14 = SdpTreeFromStream(v53, (unsigned int)v50, &v46);
        v15 = RtlNtStatusToDosError(v14);
        v5 = v15;
        if ( v15 > 0 )
          v5 = (unsigned __int16)v15 | 0x80070000;
        if ( v5 < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x10E,
            (unsigned int)"onecore\\drivers\\wdm\\bluetooth\\user\\bthserv\\server\\bluetoothapis\\lib\\bthservbthapis.cpp",
            (const char *)(unsigned int)v5,
            lpOutBuffera);
          v45 = &Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::SdpTreeTraits>::`vftable';
          if ( v46 )
          {
            if ( !(unsigned __int8)Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::SdpTreeTraits>::InternalClose(&v45) )
            {
              v31 = GetLastError();
              if ( v31 > 0 )
                v31 = (unsigned __int16)v31 | 0x80070000;
              Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v31, v32, v33);
              __debugbreak();
            }
LABEL_26:
            v46 = 0;
          }
LABEL_27:
          if ( *(_QWORD *)&InBuffer[3] )
          {
            v44 = *(_QWORD *)&InBuffer[3];
            DeviceIoControl(hObject, 0x410204u, &v44, 8u, 0, 0, 0, 0);
          }
          v10 = hObject;
          v11 = (char *)hObject - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL;
          goto LABEL_14;
        }
        memset_0(&v61, 0, 0x72Au);
        v47 = 33686017;
        v48 = 517;
        v16 = &v47;
        do
        {
          AttributeInTree = SdpFindAttributeInTree(v46, *(unsigned __int16 *)v16, &v44);
          v18 = RtlNtStatusToDosError(AttributeInTree);
          v5 = v18;
          if ( v18 > 0 )
            v5 = (unsigned __int16)v18 | 0x80070000;
          if ( v5 < 0 )
          {
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x11F,
              (unsigned int)"onecore\\drivers\\wdm\\bluetooth\\user\\bthserv\\server\\bluetoothapis\\lib\\bthservbthapis.cpp",
              (const char *)(unsigned int)v5,
              lpOutBuffera);
            v45 = &Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::SdpTreeTraits>::`vftable';
            if ( !v46 )
              goto LABEL_27;
            if ( !(unsigned __int8)Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::SdpTreeTraits>::InternalClose(&v45) )
            {
              v28 = GetLastError();
              if ( v28 > 0 )
                v28 = (unsigned __int16)v28 | 0x80070000;
              Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v28, v29, v30);
              __debugbreak();
            }
            goto LABEL_26;
          }
          if ( *(_WORD *)(v44 + 16) != 1 || *(_WORD *)(v44 + 18) != 272 || *(_DWORD *)(v44 + 24) != 2 )
          {
            v5 = -2147024809;
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x125,
              (unsigned int)"onecore\\drivers\\wdm\\bluetooth\\user\\bthserv\\server\\bluetoothapis\\lib\\bthservbthapis.cpp",
              (const char *)0x80070057LL,
              lpOutBuffera);
            v45 = &Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::SdpTreeTraits>::`vftable';
            if ( !v46 )
              goto LABEL_27;
            if ( !(unsigned __int8)Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::SdpTreeTraits>::InternalClose(&v45) )
            {
              v25 = GetLastError();
              if ( v25 > 0 )
                v25 = (unsigned __int16)v25 | 0x80070000;
              Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v25, v26, v27);
              __debugbreak();
            }
            goto LABEL_26;
          }
          switch ( *(_WORD *)v16 )
          {
            case 0x201:
              v63 = *(_WORD *)(v44 + 32);
              break;
            case 0x202:
              v64 = *(_WORD *)(v44 + 32);
              break;
            case 0x205:
              v65 = *(_WORD *)(v44 + 32);
              break;
          }
          v16 = (int *)((char *)v16 + 2);
        }
        while ( v16 != (int *)&v49 );
        v61 = *((_QWORD *)this + 1);
        v62 = 20;
        if ( DeviceIoControl(hObject, 0x411030u, &v61, 0x72Au, 0, 0, 0, 0) )
        {
          v45 = &Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::SdpTreeTraits>::`vftable';
          if ( v46 )
          {
            if ( !(unsigned __int8)Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::SdpTreeTraits>::InternalClose(&v45) )
            {
              v34 = GetLastError();
              if ( v34 > 0 )
                v34 = (unsigned __int16)v34 | 0x80070000;
              Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v34, v35, v36);
              __debugbreak();
            }
            v46 = 0;
          }
          if ( *(_QWORD *)&InBuffer[3] )
          {
            v44 = *(_QWORD *)&InBuffer[3];
            DeviceIoControl(hObject, 0x410204u, &v44, 8u, 0, 0, 0, 0);
          }
          if ( (char *)hObject - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
            CloseHandle(hObject);
          return 0;
        }
        v5 = wil::details::in1diag3::Return_GetLastError(
               retaddr,
               (void *)0x145,
               (unsigned int)"onecore\\drivers\\wdm\\bluetooth\\user\\bthserv\\server\\bluetoothapis\\lib\\bthservbthapis.cpp",
               v19);
        v45 = &Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::SdpTreeTraits>::`vftable';
        if ( v46 )
        {
          if ( !(unsigned __int8)Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::SdpTreeTraits>::InternalClose(&v45) )
          {
            v37 = GetLastError();
            if ( v37 > 0 )
              v37 = (unsigned __int16)v37 | 0x80070000;
            Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v37, v38, v39);
            JUMPOUT(0x18002472ELL);
          }
          v46 = 0;
        }
        if ( *(_QWORD *)&InBuffer[3] )
        {
          v44 = *(_QWORD *)&InBuffer[3];
          DeviceIoControl(hObject, 0x410204u, &v44, 8u, 0, 0, 0, 0);
        }
LABEL_13:
        v10 = hObject;
        v11 = (char *)hObject - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL;
LABEL_14:
        if ( v11 )
          CloseHandle(v10);
        return (unsigned int)v5;
      }
      v20 = wil::details::in1diag3::Return_Win32Msg(
              retaddr,
              (void *)0x105,
              (unsigned int)"onecore\\drivers\\wdm\\bluetooth\\user\\bthserv\\server\\bluetoothapis\\lib\\bthservbthapis.cpp",
              (const char *)0x490,
              (unsigned int)"Pnp attribute not found",
              nOutBufferSize);
      v45 = &Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::SdpTreeTraits>::`vftable';
      if ( v46 )
      {
        if ( !(unsigned __int8)Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::SdpTreeTraits>::InternalClose(&v45) )
        {
          v22 = GetLastError();
          if ( v22 > 0 )
            v22 = (unsigned __int16)v22 | 0x80070000;
          Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v22, v23, v24);
          __debugbreak();
        }
        v46 = 0;
      }
      if ( *(_QWORD *)&InBuffer[3] )
      {
        v44 = *(_QWORD *)&InBuffer[3];
LABEL_73:
        DeviceIoControl(hObject, 0x410204u, &v44, 8u, 0, 0, 0, 0);
        goto LABEL_74;
      }
      goto LABEL_74;
    }
    v21 = 251;
  }
  else
  {
    v21 = 230;
  }
  v20 = wil::details::in1diag3::Return_GetLastError(
          retaddr,
          (void *)v21,
          (unsigned int)"onecore\\drivers\\wdm\\bluetooth\\user\\bthserv\\server\\bluetoothapis\\lib\\bthservbthapis.cpp",
          v13);
  if ( *(_QWORD *)&InBuffer[3] )
  {
    v44 = *(_QWORD *)&InBuffer[3];
    goto LABEL_73;
  }
LABEL_74:
  if ( (char *)hObject - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
    CloseHandle(hObject);
  return v20;
}

```

## disassembly

```asm
0x180024004  push    rbp
0x180024006  push    rbx
0x180024007  push    rsi
0x180024008  push    rdi
0x180024009  push    r12
0x18002400b  push    r13
0x18002400d  push    r14
0x18002400f  push    r15
0x180024011  lea     rbp, [rsp-8E8h]
0x180024019  sub     rsp, 9E8h
0x180024020  mov     rax, cs:__security_cookie
0x180024027  xor     rax, rsp
0x18002402a  mov     [rbp+920h+var_50], rax
0x180024031  mov     r13, rcx
0x180024034  lea     rax, WPP_GLOBAL_Control
0x18002403b  xor     r12d, r12d
0x18002403e  mov     rcx, cs:WPP_GLOBAL_Control
0x180024045  cmp     rcx, rax
0x180024048  jz      short loc_180024052
0x18002404a  cmp     byte ptr [rcx+19h], 5
0x18002404e  mov     dl, 1
0x180024050  jnb     short loc_180024055
0x180024052  mov     dl, r12b
0x180024055  lea     rax, WPP_RECORDER_INITIALIZED
0x18002405c  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x180024063  setnz   r8b
0x180024067  test    dl, dl
0x180024069  jnz     short loc_180024070
0x18002406b  test    r8b, r8b
0x18002406e  jz      short loc_180024090
0x180024070  lea     rax, WPP_b232bbd09fa63021a92d957d702a2cb3_Traceguids
0x180024077  mov     [rsp+0A20h+lpOverlapped], rax
0x18002407c  mov     word ptr [rsp+0A20h+lpBytesReturned], 0Fh
0x180024083  mov     r9, [rcx+28h]
0x180024087  mov     rcx, [rcx+10h]
0x18002408b  call    WPP_RECORDER_AND_TRACE_SF_s
0x180024090  mov     [rsp+0A20h+hObject], r12
0x180024095  lea     rax, [rsp+0A20h+hObject]
0x18002409a  mov     [rbp+920h+var_980], rax
0x18002409e  mov     [rbp+920h+var_978], r12
0x1800240a2  mov     [rbp+920h+var_970], 1
0x1800240a6  lea     r8, [rbp+920h+var_978]
0x1800240aa  xor     edx, edx
0x1800240ac  call    BthDevnodeOpenInterfaceHandle
0x1800240b1  mov     edi, eax
0x1800240b3  cmp     [rbp+920h+var_970], r12b
0x1800240b7  jz      short loc_1800240EA
0x1800240b9  mov     r15, [rbp+920h+var_978]
0x1800240bd  mov     rsi, [rbp+920h+var_980]
0x1800240c1  mov     r14, [rsi]
0x1800240c4  lea     rdx, [r14-1]
0x1800240c8  cmp     rdx, 0FFFFFFFFFFFFFFFDh
0x1800240cc  ja      short loc_1800240E7
0x1800240ce  call    cs:__imp_GetLastError
0x1800240d4  mov     ebx, eax
0x1800240d6  mov     rcx, r14; hObject
0x1800240d9  call    cs:__imp_CloseHandle
0x1800240df  mov     ecx, ebx; dwErrCode
0x1800240e1  call    cs:__imp_SetLastError
0x1800240e7  mov     [rsi], r15
0x1800240ea  test    edi, edi
0x1800240ec  jns     short loc_180024126
0x1800240ee  mov     rcx, [rbp+928h]; this
0x1800240f5  mov     r9d, edi; char *
0x1800240f8  lea     r8, aOnecoreDrivers_4; "onecore\\drivers\\wdm\\bluetooth\\user"...
0x1800240ff  mov     edx, 0C7h; void *
0x180024104  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180024109  nop
0x18002410a  mov     rcx, [rsp+0A20h+hObject]; hObject
0x18002410f  lea     rax, [rcx-1]
0x180024113  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180024117  ja      short loc_18002411F
0x180024119  call    cs:__imp_CloseHandle
0x18002411f  mov     eax, edi
0x180024121  jmp     loc_18002467E
0x180024126  mov     [rbp+920h+var_998], r12
0x18002412a  mov     [rbp+920h+var_990], r12d
0x18002412e  mov     rax, [r13+8]
0x180024132  mov     [rbp+920h+InBuffer], rax
0x180024136  mov     [rbp+920h+var_98C], 0Ah
0x18002413a  mov     [rsp+0A20h+lpOverlapped], r12; lpOverlapped
0x18002413f  mov     [rsp+0A20h+lpBytesReturned], r12; lpBytesReturned
0x180024144  mov     r9d, 15h; nInBufferSize
0x18002414a  mov     dword ptr [rsp+0A20h+nOutBufferSize], r9d; nOutBufferSize
0x18002414f  lea     rax, [rbp+920h+InBuffer]
0x180024153  mov     [rsp+0A20h+lpOutBuffer], rax; lpOutBuffer
0x180024158  lea     r8, [rbp+920h+InBuffer]; lpInBuffer
0x18002415c  mov     edx, 410200h; dwIoControlCode
0x180024161  mov     rcx, [rsp+0A20h+hObject]; hDevice
0x180024166  call    cs:__imp_DeviceIoControl
0x18002416c  test    eax, eax
0x18002416e  jz      loc_18002460F
0x180024174  mov     edi, 100h
0x180024179  mov     r8d, edi; Size
0x18002417c  xor     edx, edx; Val
0x18002417e  lea     rcx, [rbp+920h+var_960]; void *
0x180024182  call    memset_0
0x180024187  mov     rax, [rbp+920h+var_998+4]
0x18002418b  mov     [rbp+920h+var_960], rax
0x18002418f  mov     eax, 1200h
0x180024194  mov     [rbp+920h+var_954], ax
0x180024198  lea     eax, [rdi+30h]
0x18002419b  mov     [rbp+920h+var_944], ax
0x18002419f  mov     [rbp+920h+var_864], 2050201h
0x1800241a9  mov     esi, 205h
0x1800241ae  lea     ebx, [rdi-2Fh]
0x1800241b1  mov     r8d, ebx; Size
0x1800241b4  xor     edx, edx; Val
0x1800241b6  lea     rcx, [rbp+920h+OutBuffer]; void *
0x1800241bd  call    memset_0
0x1800241c2  mov     [rsp+0A20h+lpOverlapped], r12; lpOverlapped
0x1800241c7  mov     [rsp+0A20h+lpBytesReturned], r12; lpBytesReturned
0x1800241cc  mov     dword ptr [rsp+0A20h+nOutBufferSize], ebx; char *
0x1800241d0  lea     rax, [rbp+920h+OutBuffer]
0x1800241d7  mov     [rsp+0A20h+lpOutBuffer], rax; lpOutBuffer
0x1800241dc  mov     r9d, edi; nInBufferSize
0x1800241df  lea     r8, [rbp+920h+var_960]; lpInBuffer
0x1800241e3  mov     edx, 410210h; dwIoControlCode
0x1800241e8  mov     rcx, [rsp+0A20h+hObject]; hDevice
0x1800241ed  call    cs:__imp_DeviceIoControl
0x1800241f3  test    eax, eax
0x1800241f5  jz      loc_180024608
0x1800241fb  lea     r14, ??_7?$HandleT@USdpTreeTraits@Wrappers@WRL@Microsoft@@@Wrappers@WRL@Microsoft@@6B@; const Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::SdpTreeTraits>::`vftable'
0x180024202  mov     [rsp+0A20h+var_9C0], r14
0x180024207  mov     [rsp+0A20h+var_9B8], r12
0x18002420c  mov     [rsp+0A20h+var_9C8], r12
0x180024211  mov     [rbp+920h+var_988], r12
0x180024215  mov     [rsp+0A20h+var_9A8], r12d
0x18002421a  lea     rax, [rsp+0A20h+var_9A8]
0x18002421f  mov     [rsp+0A20h+lpOutBuffer], rax; int
0x180024224  lea     r9, [rbp+920h+var_988]
0x180024228  xor     r8d, r8d
0x18002422b  mov     edx, [rbp+920h+var_12C]
0x180024231  lea     rcx, [rbp+920h+var_128]
0x180024238  call    SdpGetNextElement
0x18002423d  mov     rcx, [rbp+920h+var_988]
0x180024241  test    rcx, rcx
0x180024244  jz      loc_1800245A9
0x18002424a  mov     edx, [rsp+0A20h+var_9A8]
0x18002424e  test    edx, edx
0x180024250  jz      loc_1800245A9
0x180024256  lea     r8, [rsp+0A20h+var_9B8]
0x18002425b  call    SdpTreeFromStream
0x180024260  mov     ecx, eax; Status
0x180024262  call    cs:__imp_RtlNtStatusToDosError
0x180024268  mov     edi, eax
0x18002426a  mov     ebx, 80070000h
0x18002426f  test    eax, eax
0x180024271  jle     short loc_180024278
0x180024273  movzx   edi, ax
0x180024276  or      edi, ebx
0x180024278  test    edi, edi
0x18002427a  jns     loc_18002430E
0x180024280  mov     rcx, [rbp+928h]; this
0x180024287  mov     r9d, edi; char *
0x18002428a  lea     r8, aOnecoreDrivers_4; "onecore\\drivers\\wdm\\bluetooth\\user"...
0x180024291  mov     edx, 10Eh; void *
0x180024296  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002429b  mov     [rsp+0A20h+var_9C0], r14
0x1800242a0  cmp     [rsp+0A20h+var_9B8], r12
0x1800242a5  jz      short loc_1800242BE
0x1800242a7  lea     rcx, [rsp+0A20h+var_9C0]
0x1800242ac  call    ?InternalClose@?$HandleT@USdpTreeTraits@Wrappers@WRL@Microsoft@@@Wrappers@WRL@Microsoft@@MEAA_NXZ; Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::SdpTreeTraits>::InternalClose(void)
0x1800242b1  test    al, al
0x1800242b3  jz      loc_1800246EA
0x1800242b9  mov     [rsp+0A20h+var_9B8], r12
0x1800242be  mov     rax, [rbp+920h+var_998+4]
0x1800242c2  test    rax, rax
0x1800242c5  jz      short loc_1800242FC
0x1800242c7  mov     [rsp+0A20h+var_9C8], rax
0x1800242cc  mov     [rsp+0A20h+lpOverlapped], r12; lpOverlapped
0x1800242d1  mov     [rsp+0A20h+lpBytesReturned], r12; lpBytesReturned
0x1800242d6  mov     dword ptr [rsp+0A20h+nOutBufferSize], r12d; nOutBufferSize
0x1800242db  mov     [rsp+0A20h+lpOutBuffer], r12; lpOutBuffer
0x1800242e0  mov     r9d, 8; nInBufferSize
0x1800242e6  lea     r8, [rsp+0A20h+var_9C8]; lpInBuffer
0x1800242eb  mov     edx, 410204h; dwIoControlCode
0x1800242f0  mov     rcx, [rsp+0A20h+hObject]; hDevice
0x1800242f5  call    cs:__imp_DeviceIoControl
0x1800242fb  nop
0x1800242fc  mov     rcx, [rsp+0A20h+hObject]
0x180024301  lea     rdx, [rcx-1]
0x180024305  cmp     rdx, 0FFFFFFFFFFFFFFFDh
0x180024309  jmp     loc_180024117
0x18002430e  mov     r15d, 72Ah
0x180024314  mov     r8d, r15d; Size
0x180024317  xor     edx, edx; Val
0x180024319  lea     rcx, [rbp+920h+var_860]; void *
0x180024320  call    memset_0
0x180024325  mov     [rsp+0A20h+var_9B0], 2020201h
0x18002432d  mov     [rsp+0A20h+var_9AC], si
0x180024332  lea     rsi, [rsp+0A20h+var_9B0]
0x180024337  lea     r8, [rsp+0A20h+var_9C8]
0x18002433c  movzx   edx, word ptr [rsi]
0x18002433f  mov     rcx, [rsp+0A20h+var_9B8]
0x180024344  call    SdpFindAttributeInTree
0x180024349  mov     ecx, eax; Status
0x18002434b  call    cs:__imp_RtlNtStatusToDosError
0x180024351  mov     edi, eax
0x180024353  test    eax, eax
0x180024355  jle     short loc_18002435C
0x180024357  movzx   edi, ax
0x18002435a  or      edi, ebx
0x18002435c  test    edi, edi
0x18002435e  js      loc_180024567
0x180024364  mov     rdx, [rsp+0A20h+var_9C8]
0x180024369  cmp     word ptr [rdx+10h], 1
0x18002436e  jnz     loc_180024520
0x180024374  mov     eax, 110h
0x180024379  cmp     [rdx+12h], ax
0x18002437d  jnz     loc_180024520
0x180024383  cmp     dword ptr [rdx+18h], 2
0x180024387  jnz     loc_180024520
0x18002438d  movzx   ecx, word ptr [rsi]
0x180024390  sub     ecx, 201h
0x180024396  jz      short loc_1800243BC
0x180024398  sub     ecx, 1
0x18002439b  jz      short loc_1800243AF
0x18002439d  cmp     ecx, 3
0x1800243a0  jnz     short loc_1800243C7
0x1800243a2  movzx   eax, word ptr [rdx+20h]
0x1800243a6  mov     [rbp+920h+var_84A], ax
0x1800243ad  jmp     short loc_1800243C7
0x1800243af  movzx   eax, word ptr [rdx+20h]
0x1800243b3  mov     [rbp+920h+var_84E], ax
0x1800243ba  jmp     short loc_1800243C7
0x1800243bc  movzx   eax, word ptr [rdx+20h]
0x1800243c0  mov     [rbp+920h+var_850], ax
0x1800243c7  add     rsi, 2
0x1800243cb  lea     rax, [rsp+0A20h+var_9AA]
0x1800243d0  cmp     rsi, rax
0x1800243d3  jnz     loc_180024337
0x1800243d9  mov     rax, [r13+8]
0x1800243dd  mov     [rbp+920h+var_860], rax
0x1800243e4  mov     [rbp+920h+var_854], 14h
0x1800243ee  mov     [rsp+0A20h+lpOverlapped], r12; lpOverlapped
0x1800243f3  mov     [rsp+0A20h+lpBytesReturned], r12; lpBytesReturned
0x1800243f8  mov     dword ptr [rsp+0A20h+nOutBufferSize], r12d; nOutBufferSize
0x1800243fd  mov     [rsp+0A20h+lpOutBuffer], r12; lpOutBuffer
0x180024402  mov     r9d, r15d; nInBufferSize
0x180024405  lea     r8, [rbp+920h+var_860]; lpInBuffer
0x18002440c  mov     edx, 411030h; dwIoControlCode
0x180024411  mov     rcx, [rsp+0A20h+hObject]; hDevice
0x180024416  call    cs:__imp_DeviceIoControl
0x18002441c  test    eax, eax
0x18002441e  jz      short loc_18002449D
0x180024420  mov     [rsp+0A20h+var_9C0], r14
0x180024425  cmp     [rsp+0A20h+var_9B8], r12
0x18002442a  jz      short loc_180024443
0x18002442c  lea     rcx, [rsp+0A20h+var_9C0]
0x180024431  call    ?InternalClose@?$HandleT@USdpTreeTraits@Wrappers@WRL@Microsoft@@@Wrappers@WRL@Microsoft@@MEAA_NXZ; Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::SdpTreeTraits>::InternalClose(void)
0x180024436  test    al, al
0x180024438  jz      loc_180024701
0x18002443e  mov     [rsp+0A20h+var_9B8], r12
0x180024443  mov     rax, [rbp+920h+var_998+4]
0x180024447  test    rax, rax
0x18002444a  jz      short loc_180024481
0x18002444c  mov     [rsp+0A20h+var_9C8], rax
0x180024451  mov     [rsp+0A20h+lpOverlapped], r12; lpOverlapped
0x180024456  mov     [rsp+0A20h+lpBytesReturned], r12; lpBytesReturned
0x18002445b  mov     dword ptr [rsp+0A20h+nOutBufferSize], r12d; nOutBufferSize
0x180024460  mov     [rsp+0A20h+lpOutBuffer], r12; lpOutBuffer
0x180024465  mov     r9d, 8; nInBufferSize
0x18002446b  lea     r8, [rsp+0A20h+var_9C8]; lpInBuffer
0x180024470  mov     edx, 410204h; dwIoControlCode
0x180024475  mov     rcx, [rsp+0A20h+hObject]; hDevice
0x18002447a  call    cs:__imp_DeviceIoControl
0x180024480  nop
0x180024481  mov     rcx, [rsp+0A20h+hObject]; hObject
0x180024486  lea     rax, [rcx-1]
0x18002448a  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18002448e  ja      short loc_180024496
0x180024490  call    cs:__imp_CloseHandle
0x180024496  xor     eax, eax
0x180024498  jmp     loc_18002467E
0x18002449d  mov     rcx, [rbp+928h]; this
0x1800244a4  lea     r8, aOnecoreDrivers_4; "onecore\\drivers\\wdm\\bluetooth\\user"...
0x1800244ab  mov     edx, 145h; void *
0x1800244b0  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800244b5  mov     edi, eax
0x1800244b7  mov     [rsp+0A20h+var_9C0], r14
0x1800244bc  cmp     [rsp+0A20h+var_9B8], r12
0x1800244c1  jz      short loc_1800244DA
0x1800244c3  lea     rcx, [rsp+0A20h+var_9C0]
0x1800244c8  call    ?InternalClose@?$HandleT@USdpTreeTraits@Wrappers@WRL@Microsoft@@@Wrappers@WRL@Microsoft@@MEAA_NXZ; Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::SdpTreeTraits>::InternalClose(void)
0x1800244cd  test    al, al
0x1800244cf  jz      loc_180024718
0x1800244d5  mov     [rsp+0A20h+var_9B8], r12
0x1800244da  mov     rax, [rbp+920h+var_998+4]
0x1800244de  test    rax, rax
0x1800244e1  jz      loc_18002410A
0x1800244e7  mov     [rsp+0A20h+var_9C8], rax
0x1800244ec  mov     [rsp+0A20h+lpOverlapped], r12; lpOverlapped
0x1800244f1  mov     [rsp+0A20h+lpBytesReturned], r12; lpBytesReturned
0x1800244f6  mov     dword ptr [rsp+0A20h+nOutBufferSize], r12d; nOutBufferSize
0x1800244fb  mov     [rsp+0A20h+lpOutBuffer], r12; lpOutBuffer
0x180024500  mov     r9d, 8; nInBufferSize
0x180024506  lea     r8, [rsp+0A20h+var_9C8]; lpInBuffer
0x18002450b  mov     edx, 410204h; dwIoControlCode
0x180024510  mov     rcx, [rsp+0A20h+hObject]; hDevice
  ... truncated ...
```
