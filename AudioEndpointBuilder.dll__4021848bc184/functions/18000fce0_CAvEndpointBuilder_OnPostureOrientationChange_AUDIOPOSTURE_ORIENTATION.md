# CAvEndpointBuilder::OnPostureOrientationChange(AUDIOPOSTURE_ORIENTATION *)

- ea: `0x18000fce0`
- end: `0x180010015`
- name: `?OnPostureOrientationChange@CAvEndpointBuilder@@AEAAJPEAW4AUDIOPOSTURE_ORIENTATION@@@Z`
- size: `821`
- prototype: `__int64 __fastcall(LPCRITICAL_SECTION lpCriticalSection, enum AUDIOPOSTURE_ORIENTATION *)`
- caller_count: `2`
- callee_count: `7`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x18000fbc0`
- `0x180051294`

## callees

- `0x180006b0c`
- `0x18000fce0`
- `0x18001001c`
- `0x180010da8`
- `0x18001707c`
- `0x180034c5c`
- `0x180068010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000fe5e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000fec3`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000ff0e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000ff77`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000ffe0`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000fe5e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000fec3`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000ff0e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000ff77`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000ffe0`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000fcff`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000fcff`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000ff41`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000ff41`

## string_xrefs

- `0x18000fe94`: `avcore\audiocore\server\audioendpointbuilder\dll\avendpointbuilder.cpp`
- `0x18000fef9`: `avcore\audiocore\server\audioendpointbuilder\dll\avendpointbuilder.cpp`
- `0x18000ff62`: `avcore\audiocore\server\audioendpointbuilder\dll\avendpointbuilder.cpp`
- `0x18000ffcb`: `avcore\audiocore\server\audioendpointbuilder\dll\avendpointbuilder.cpp`
- `0x18000fffe`: `avcore\audiocore\server\audioendpointbuilder\dll\avendpointbuilder.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall CAvEndpointBuilder::OnPostureOrientationChange(
        LPCRITICAL_SECTION lpCriticalSection,
        enum AUDIOPOSTURE_ORIENTATION *a2)
{
  _DWORD *OwningThread; // rcx
  struct IUnknown *v5; // rcx
  HRESULT (__stdcall *QueryInterface)(IUnknown *, const IID *const, void **); // rbx
  __int64 v7; // rdx
  int v8; // eax
  unsigned int v9; // ebx
  int v10; // eax
  unsigned int v11; // ebx
  unsigned int i; // ebx
  __int64 v13; // rax
  int v14; // eax
  unsigned int v15; // esi
  int v16; // eax
  int v18; // [rsp+20h] [rbp-48h]
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+0h]
  unsigned int v20; // [rsp+70h] [rbp+8h] BYREF
  __int64 *v21; // [rsp+80h] [rbp+18h] BYREF
  struct IMMDevice *v22; // [rsp+88h] [rbp+20h] BYREF

  v20 = 0;
  v21 = 0;
  EnterCriticalSection(lpCriticalSection);
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x80000) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 113, WPP_2d9c823d16a63a6be100bbcd5714e122_Traceguids);
  }
  OwningThread = lpCriticalSection[1].OwningThread;
  if ( OwningThread || (OwningThread = CoTaskMemAlloc(4u), (lpCriticalSection[1].OwningThread = OwningThread) != 0) )
  {
    *OwningThread = *(_DWORD *)a2;
    v5 = g_DeviceEnumerator;
    QueryInterface = g_DeviceEnumerator->lpVtbl[1].QueryInterface;
    v7 = (__int64)v21;
    v21 = 0;
    if ( v7 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v7 + 16LL))(v7);
      v5 = g_DeviceEnumerator;
    }
    v8 = ((__int64 (__fastcall *)(struct IUnknown *, __int64, __int64, __int64 **))QueryInterface)(v5, 2, 9, &v21);
    v9 = v8;
    if ( v8 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x2E01,
        (unsigned int)"avcore\\audiocore\\server\\audioendpointbuilder\\dll\\avendpointbuilder.cpp",
        (const char *)(unsigned int)v8,
        v18);
      LeaveCriticalSection(lpCriticalSection);
      if ( v21 )
        (*(void (__fastcall **)(__int64 *))(*v21 + 16))(v21);
      return v9;
    }
    else
    {
      v10 = (*(__int64 (__fastcall **)(__int64 *, unsigned int *))(*v21 + 24))(v21, &v20);
      v11 = v10;
      if ( v10 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x2E04,
          (unsigned int)"avcore\\audiocore\\server\\audioendpointbuilder\\dll\\avendpointbuilder.cpp",
          (const char *)(unsigned int)v10,
          v18);
        LeaveCriticalSection(lpCriticalSection);
        ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((__int64 *)&v21);
        return v11;
      }
      else
      {
        for ( i = 0; i < v20; ++i )
        {
          v22 = 0;
          v13 = *v21;
          v22 = 0;
          v14 = (*(__int64 (__fastcall **)(__int64 *, _QWORD, struct IMMDevice **))(v13 + 32))(v21, i, &v22);
          v15 = v14;
          if ( v14 < 0 )
          {
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x2E0A,
              (unsigned int)"avcore\\audiocore\\server\\audioendpointbuilder\\dll\\avendpointbuilder.cpp",
              (const char *)(unsigned int)v14,
              v18);
            if ( v22 )
              ((void (__fastcall *)(struct IMMDevice *))v22->lpVtbl->Release)(v22);
            LeaveCriticalSection(lpCriticalSection);
            if ( v21 )
              (*(void (__fastcall **)(__int64 *))(*v21 + 16))(v21);
            return v15;
          }
          v16 = SetOrientationProperty(v22, a2);
          if ( v16 < 0 )
            wil::details::in1diag3::_Log_Hr(
              retaddr,
              (void *)0x2E0C,
              (int)"avcore\\audiocore\\server\\audioendpointbuilder\\dll\\avendpointbuilder.cpp",
              (const char *)(unsigned int)v16);
          if ( v22 )
            ((void (__fastcall *)(struct IMMDevice *))v22->lpVtbl->Release)(v22);
        }
        LeaveCriticalSection(lpCriticalSection);
        if ( v21 )
          (*(void (__fastcall **)(__int64 *))(*v21 + 16))(v21);
        return 0;
      }
    }
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x2DFA,
      (unsigned int)"avcore\\audiocore\\server\\audioendpointbuilder\\dll\\avendpointbuilder.cpp",
      (const char *)0x8007000ELL,
      v18);
    LeaveCriticalSection(lpCriticalSection);
    if ( v21 )
      (*(void (__fastcall **)(__int64 *))(*v21 + 16))(v21);
    return 2147942414LL;
  }
}

```

## disassembly

```asm
0x18000fce0  push    rbx
0x18000fce2  push    rbp
0x18000fce3  push    rsi
0x18000fce4  push    rdi
0x18000fce5  push    r14
0x18000fce7  sub     rsp, 40h
0x18000fceb  mov     r14, rdx
0x18000fcee  mov     rdi, rcx
0x18000fcf1  xor     ebp, ebp
0x18000fcf3  mov     [rsp+68h+arg_0], ebp
0x18000fcf7  mov     [rsp+68h+arg_10], rbp
0x18000fcff  call    cs:__imp_EnterCriticalSection
0x18000fd05  mov     [rsp+68h+var_38], rdi
0x18000fd0a  lea     rax, WPP_GLOBAL_Control
0x18000fd11  mov     rcx, cs:WPP_GLOBAL_Control
0x18000fd18  cmp     rcx, rax
0x18000fd1b  jnz     loc_18000FE2A
0x18000fd21  mov     rcx, [rdi+38h]
0x18000fd25  test    rcx, rcx
0x18000fd28  jz      loc_18000FF3C
0x18000fd2e  mov     eax, [r14]
0x18000fd31  mov     [rcx], eax
0x18000fd33  mov     rcx, cs:?g_DeviceEnumerator@@3PEAUIMMDeviceEnumerator@@EA; IMMDeviceEnumerator * g_DeviceEnumerator
0x18000fd3a  mov     rax, [rcx]
0x18000fd3d  mov     rbx, [rax+18h]
0x18000fd41  mov     rdx, [rsp+68h+arg_10]
0x18000fd49  mov     [rsp+68h+arg_10], rbp
0x18000fd51  test    rdx, rdx
0x18000fd54  jnz     loc_18000FFA8
0x18000fd5a  lea     r9, [rsp+68h+arg_10]
0x18000fd62  mov     edx, 2
0x18000fd67  mov     r8d, 9
0x18000fd6d  mov     rax, rbx
0x18000fd70  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000fd75  mov     ebx, eax
0x18000fd77  test    eax, eax
0x18000fd79  js      loc_18000FEF1
0x18000fd7f  mov     rcx, [rsp+68h+arg_10]
0x18000fd87  mov     rax, [rcx]
0x18000fd8a  lea     rdx, [rsp+68h+arg_0]
0x18000fd8f  mov     rax, [rax+18h]
0x18000fd93  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000fd98  mov     ebx, eax
0x18000fd9a  test    eax, eax
0x18000fd9c  js      loc_18000FFC3
0x18000fda2  mov     ebx, ebp
0x18000fda4  cmp     ebx, [rsp+68h+arg_0]
0x18000fda8  jnb     loc_18000FE5B
0x18000fdae  mov     [rsp+68h+arg_18], rbp
0x18000fdb6  mov     rcx, [rsp+68h+arg_10]
0x18000fdbe  mov     rax, [rcx]
0x18000fdc1  mov     [rsp+68h+arg_18], rbp
0x18000fdc9  lea     r8, [rsp+68h+arg_18]
0x18000fdd1  mov     edx, ebx
0x18000fdd3  mov     rax, [rax+20h]
0x18000fdd7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000fddc  mov     esi, eax
0x18000fdde  test    eax, eax
0x18000fde0  js      loc_18000FE8C
0x18000fde6  mov     r8d, 4; unsigned int
0x18000fdec  mov     rdx, r14; void *
0x18000fdef  mov     rcx, [rsp+68h+arg_18]; struct IMMDevice *
0x18000fdf7  call    ?SetOrientationProperty@@YAJPEAUIMMDevice@@PEAXK@Z; SetOrientationProperty(IMMDevice *,void *,ulong)
0x18000fdfc  mov     rcx, [rsp+68h]; this
0x18000fe01  test    eax, eax
0x18000fe03  js      loc_18000FFFB
0x18000fe09  mov     rcx, [rsp+68h+arg_18]
0x18000fe11  test    rcx, rcx
0x18000fe14  jz      short loc_18000FE23
0x18000fe16  mov     rax, [rcx]
0x18000fe19  mov     rax, [rax+10h]
0x18000fe1d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000fe22  nop
0x18000fe23  inc     ebx
0x18000fe25  jmp     loc_18000FDA4
0x18000fe2a  test    dword ptr [rcx+1Ch], 80000h
0x18000fe31  jz      loc_18000FD21
0x18000fe37  cmp     byte ptr [rcx+19h], 4
0x18000fe3b  jb      loc_18000FD21
0x18000fe41  mov     edx, 71h ; 'q'
0x18000fe46  lea     r8, WPP_2d9c823d16a63a6be100bbcd5714e122_Traceguids
0x18000fe4d  mov     rcx, [rcx+10h]
0x18000fe51  call    WPP_SF_
0x18000fe56  jmp     loc_18000FD21
0x18000fe5b  mov     rcx, rdi; lpCriticalSection
0x18000fe5e  call    cs:__imp_LeaveCriticalSection
0x18000fe64  nop
0x18000fe65  mov     rcx, [rsp+68h+arg_10]
0x18000fe6d  test    rcx, rcx
0x18000fe70  jz      short loc_18000FE7F
0x18000fe72  mov     rax, [rcx]
0x18000fe75  mov     rax, [rax+10h]
0x18000fe79  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000fe7e  nop
0x18000fe7f  xor     eax, eax
0x18000fe81  add     rsp, 40h
0x18000fe85  pop     r14
0x18000fe87  pop     rdi
0x18000fe88  pop     rsi
0x18000fe89  pop     rbp
0x18000fe8a  pop     rbx
0x18000fe8b  retn
0x18000fe8c  mov     rcx, [rsp+68h]; this
0x18000fe91  mov     r9d, esi; char *
0x18000fe94  lea     r8, aAvcoreAudiocor_6; "avcore\\audiocore\\server\\audioendpoin"...
0x18000fe9b  mov     edx, 2E0Ah; void *
0x18000fea0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000fea5  nop
0x18000fea6  mov     rcx, [rsp+68h+arg_18]
0x18000feae  test    rcx, rcx
0x18000feb1  jz      short loc_18000FEC0
0x18000feb3  mov     rax, [rcx]
0x18000feb6  mov     rax, [rax+10h]
0x18000feba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000febf  nop
0x18000fec0  mov     rcx, rdi; lpCriticalSection
0x18000fec3  call    cs:__imp_LeaveCriticalSection
0x18000fec9  nop
0x18000feca  mov     rcx, [rsp+68h+arg_10]
0x18000fed2  test    rcx, rcx
0x18000fed5  jz      short loc_18000FEE4
0x18000fed7  mov     rax, [rcx]
0x18000feda  mov     rax, [rax+10h]
0x18000fede  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000fee3  nop
0x18000fee4  mov     eax, esi
0x18000fee6  add     rsp, 40h
0x18000feea  pop     r14
0x18000feec  pop     rdi
0x18000feed  pop     rsi
0x18000feee  pop     rbp
0x18000feef  pop     rbx
0x18000fef0  retn
0x18000fef1  mov     rcx, [rsp+68h]; this
0x18000fef6  mov     r9d, ebx; char *
0x18000fef9  lea     r8, aAvcoreAudiocor_6; "avcore\\audiocore\\server\\audioendpoin"...
0x18000ff00  mov     edx, 2E01h; void *
0x18000ff05  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000ff0a  nop
0x18000ff0b  mov     rcx, rdi; lpCriticalSection
0x18000ff0e  call    cs:__imp_LeaveCriticalSection
0x18000ff14  nop
0x18000ff15  mov     rcx, [rsp+68h+arg_10]
0x18000ff1d  test    rcx, rcx
0x18000ff20  jz      short loc_18000FF2F
0x18000ff22  mov     rax, [rcx]
0x18000ff25  mov     rax, [rax+10h]
0x18000ff29  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ff2e  nop
0x18000ff2f  mov     eax, ebx
0x18000ff31  add     rsp, 40h
0x18000ff35  pop     r14
0x18000ff37  pop     rdi
0x18000ff38  pop     rsi
0x18000ff39  pop     rbp
0x18000ff3a  pop     rbx
0x18000ff3b  retn
0x18000ff3c  mov     ecx, 4; cb
0x18000ff41  call    cs:__imp_CoTaskMemAlloc
0x18000ff47  mov     rcx, rax
0x18000ff4a  mov     [rdi+38h], rax
0x18000ff4e  test    rax, rax
0x18000ff51  jnz     loc_18000FD2E
0x18000ff57  mov     rcx, [rsp+68h]; this
0x18000ff5c  mov     r9d, 8007000Eh; char *
0x18000ff62  lea     r8, aAvcoreAudiocor_6; "avcore\\audiocore\\server\\audioendpoin"...
0x18000ff69  mov     edx, 2DFAh; void *
0x18000ff6e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000ff73  nop
0x18000ff74  mov     rcx, rdi; lpCriticalSection
0x18000ff77  call    cs:__imp_LeaveCriticalSection
0x18000ff7d  nop
0x18000ff7e  mov     rcx, [rsp+68h+arg_10]
0x18000ff86  test    rcx, rcx
0x18000ff89  jz      short loc_18000FF98
0x18000ff8b  mov     rdx, [rcx]
0x18000ff8e  mov     rax, [rdx+10h]
0x18000ff92  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ff97  nop
0x18000ff98  mov     eax, 8007000Eh
0x18000ff9d  add     rsp, 40h
0x18000ffa1  pop     r14
0x18000ffa3  pop     rdi
0x18000ffa4  pop     rsi
0x18000ffa5  pop     rbp
0x18000ffa6  pop     rbx
0x18000ffa7  retn
0x18000ffa8  mov     rax, [rdx]
0x18000ffab  mov     rcx, rdx
0x18000ffae  mov     rax, [rax+10h]
0x18000ffb2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ffb7  mov     rcx, cs:?g_DeviceEnumerator@@3PEAUIMMDeviceEnumerator@@EA; IMMDeviceEnumerator * g_DeviceEnumerator
0x18000ffbe  jmp     loc_18000FD5A
0x18000ffc3  mov     rcx, [rsp+68h]; this
0x18000ffc8  mov     r9d, ebx; char *
0x18000ffcb  lea     r8, aAvcoreAudiocor_6; "avcore\\audiocore\\server\\audioendpoin"...
0x18000ffd2  mov     edx, 2E04h; void *
0x18000ffd7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000ffdc  nop
0x18000ffdd  mov     rcx, rdi; lpCriticalSection
0x18000ffe0  call    cs:__imp_LeaveCriticalSection
0x18000ffe6  nop
0x18000ffe7  lea     rcx, [rsp+68h+arg_10]
0x18000ffef  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18000fff4  mov     eax, ebx
0x18000fff6  jmp     loc_18000FE81
0x18000fffb  mov     r9d, eax; char *
0x18000fffe  lea     r8, aAvcoreAudiocor_6; "avcore\\audiocore\\server\\audioendpoin"...
0x180010005  mov     edx, 2E0Ch; void *
0x18001000a  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18001000f  jmp     loc_18000FE09
```
