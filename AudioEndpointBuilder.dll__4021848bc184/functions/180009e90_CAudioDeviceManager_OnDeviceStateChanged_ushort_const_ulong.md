# CAudioDeviceManager::OnDeviceStateChanged(ushort const *,ulong)

- ea: `0x180009e90`
- end: `0x18000a462`
- name: `?OnDeviceStateChanged@CAudioDeviceManager@@UEAAJPEBGK@Z`
- size: `1490`
- prototype: `__int64 __fastcall(struct IMMDeviceVtbl *this, const unsigned __int16 *, int)`
- caller_count: `1`
- callee_count: `10`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x180009bd8`

## callees

- `0x180006b0c`
- `0x180009e90`
- `0x18000ab60`
- `0x18000abf0`
- `0x180010da8`
- `0x18001707c`
- `0x180029024`
- `0x180035eb4`
- `0x18003f7a4`
- `0x180068010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180009ee1`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180009fe1`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180009ee1`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180009fe1`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180009ed0`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180009fd0`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180009ed0`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180009fd0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a269`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a269`
- `api-ms-win-core-io-l1-1-0!PostQueuedCompletionStatus` at `0x18000a25b`
- `api-ms-win-core-io-l1-1-0!PostQueuedCompletionStatus` at `0x18000a25b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000a065`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000a182`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000a065`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000a182`

## string_xrefs

- `0x18000a33c`: `avcore\audiocore\server\audioendpointbuilder\dll\audiodevice.cpp`
- `0x18000a370`: `avcore\audiocore\server\audioendpointbuilder\dll\audiodevice.cpp`
- `0x18000a3a5`: `avcore\audiocore\server\audioendpointbuilder\dll\audiodevice.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
__int64 __fastcall CAudioDeviceManager::OnDeviceStateChanged(
        struct IMMDeviceVtbl *this,
        const unsigned __int16 *a2,
        int a3)
{
  const unsigned __int16 *v4; // rdi
  MMNotification_Event *v6; // r12
  HANDLE v7; // rax
  struct IMMDevice *v8; // r14
  int v9; // ebp
  __int64 v10; // r9
  unsigned __int16 *v11; // rax
  int v13; // ebx
  int v14; // eax
  unsigned int v15; // ebx
  int v16; // eax
  HANDLE ProcessHeap; // rax
  unsigned __int64 v18; // rbx
  unsigned __int64 v19; // rsi
  _WORD *v20; // rax
  _WORD *v21; // r10
  unsigned __int64 v22; // rcx
  unsigned __int16 *v23; // rdx
  __int64 v24; // r8
  unsigned __int16 v25; // ax
  __int64 v26; // r9
  unsigned __int16 *v27; // rax
  unsigned __int64 v28; // rbx
  unsigned __int64 v29; // rsi
  _WORD *v30; // rax
  _WORD *v31; // r10
  unsigned __int64 v32; // rcx
  unsigned __int16 *v33; // rdx
  __int64 v34; // r8
  unsigned __int16 v35; // ax
  __int64 v36; // rsi
  bool v37; // cf
  __int64 v38; // rsi
  int v39; // ebx
  int v40; // [rsp+20h] [rbp-58h]
  int v41; // [rsp+20h] [rbp-58h]
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+0h]
  struct IMMDevice *v43; // [rsp+98h] [rbp+20h] BYREF

  v4 = a2;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x80000) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_Sd(*((_QWORD *)WPP_GLOBAL_Control + 2), 28, a3, (_DWORD)a2, a3);
  }
  if ( a3 == 4 )
    goto LABEL_3;
  v13 = a3 - 1;
  if ( !v13 )
  {
    v43 = 0;
    v14 = ((__int64 (__fastcall *)(struct IUnknown *, const unsigned __int16 *, struct IMMDevice **))g_DeviceEnumerator->lpVtbl[1].Release)(
            g_DeviceEnumerator,
            v4,
            &v43);
    v15 = v14;
    if ( v14 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x557,
        (unsigned int)"avcore\\audiocore\\server\\audioendpointbuilder\\dll\\audiodevice.cpp",
        (const char *)(unsigned int)v14,
        v40);
      if ( v43 )
        ((void (__fastcall *)(struct IMMDevice *))v43->lpVtbl->Release)(v43);
    }
    else
    {
      v16 = ClearVolatilePropertyStoresFromEndpoint(v43);
      v15 = v16;
      if ( v16 >= 0 )
      {
        if ( v43 )
          ((void (__fastcall *)(struct IMMDevice *))v43->lpVtbl->Release)(v43);
LABEL_20:
        v6 = 0;
        ProcessHeap = GetProcessHeap();
        v8 = (struct IMMDevice *)HeapAlloc(ProcessHeap, 0, 0x58u);
        v43 = v8;
        if ( !v8 )
          goto LABEL_4;
        v8->lpVtbl = (struct IMMDeviceVtbl *)&MMNotification_Event::`vftable';
        LODWORD(v8[1].lpVtbl) = 1;
        v8[2].lpVtbl = 0;
        v8[3].lpVtbl = 0;
        v8[6].lpVtbl = 0;
        v8[10].lpVtbl = this;
        if ( v4 )
        {
          v18 = -1;
          do
            ++v18;
          while ( v4[v18] );
          v8[2].lpVtbl = 0;
          v19 = v18 + 1;
          if ( v18 + 1 >= v18 && is_mul_ok(v19, 2u) )
          {
            v20 = CoTaskMemAlloc(2 * v19);
            v21 = v20;
            v8[2].lpVtbl = (struct IMMDeviceVtbl *)v20;
            if ( v20 )
              v9 = 0;
            else
              v9 = -2147024882;
            if ( v9 < 0 )
              goto LABEL_11;
            if ( (v20 || v18 == -1) && v19 <= 0x7FFFFFFF )
            {
              if ( v18 >= 0x7FFFFFFF )
              {
                if ( v18 != -1 )
                  *v20 = 0;
              }
              else
              {
                v22 = v18 + 1;
                v23 = v20;
                v24 = 0;
                do
                {
                  if ( !v18 )
                    break;
                  v25 = *v4;
                  if ( !*v4 )
                    break;
                  ++v4;
                  *v23++ = v25;
                  --v18;
                  ++v24;
                  --v22;
                }
                while ( v22 );
                v26 = v24 - 1;
                if ( v22 )
                  v26 = v24;
                v27 = v23 - 1;
                if ( v22 )
                  v27 = v23;
                *v27 = 0;
                if ( v22 )
                {
                  v37 = v19 == v26;
                  v38 = v19 - v26;
                  if ( !v37 && v38 != 1 && (unsigned __int64)(2 * v38) > 2 )
                    memset_0(&v21[v26 + 1], 0, 2 * v38 - 2);
                }
              }
            }
            else
            {
              *v20 = 0;
            }
          }
          else
          {
            v9 = -2147024362;
          }
        }
        else
        {
          v9 = 0;
        }
        if ( v9 < 0 )
          goto LABEL_11;
        goto LABEL_42;
      }
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x559,
        (unsigned int)"avcore\\audiocore\\server\\audioendpointbuilder\\dll\\audiodevice.cpp",
        (const char *)(unsigned int)v16,
        v40);
      ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v43);
    }
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x583,
      (unsigned int)"avcore\\audiocore\\server\\audioendpointbuilder\\dll\\audiodevice.cpp",
      (const char *)v15,
      v41);
    goto LABEL_20;
  }
  v39 = v13 - 1;
  if ( v39 && v39 != 6 )
    return 0;
LABEL_3:
  v6 = 0;
  v7 = GetProcessHeap();
  v8 = (struct IMMDevice *)HeapAlloc(v7, 0, 0x58u);
  v43 = v8;
  if ( !v8 )
  {
LABEL_4:
    v9 = -2147024882;
    goto LABEL_12;
  }
  v8->lpVtbl = (struct IMMDeviceVtbl *)&MMNotification_Event::`vftable';
  LODWORD(v8[1].lpVtbl) = 3;
  v8[2].lpVtbl = 0;
  v8[3].lpVtbl = 0;
  v8[6].lpVtbl = 0;
  v8[10].lpVtbl = this;
  if ( v4 )
  {
    v28 = -1;
    do
      ++v28;
    while ( v4[v28] );
    v8[2].lpVtbl = 0;
    v29 = v28 + 1;
    if ( v28 + 1 >= v28 && is_mul_ok(v29, 2u) )
    {
      v30 = CoTaskMemAlloc(2 * v29);
      v31 = v30;
      v8[2].lpVtbl = (struct IMMDeviceVtbl *)v30;
      if ( v30 )
        v9 = 0;
      else
        v9 = -2147024882;
      if ( v9 < 0 )
        goto LABEL_11;
      if ( (v30 || v28 == -1) && v29 <= 0x7FFFFFFF )
      {
        if ( v28 >= 0x7FFFFFFF )
        {
          if ( v28 != -1 )
            *v30 = 0;
        }
        else
        {
          v32 = v28 + 1;
          v33 = v30;
          v34 = 0;
          do
          {
            if ( !v28 )
              break;
            v35 = *v4;
            if ( !*v4 )
              break;
            ++v4;
            *v33++ = v35;
            --v28;
            ++v34;
            --v32;
          }
          while ( v32 );
          v10 = v34 - 1;
          if ( v32 )
            v10 = v34;
          v11 = v33 - 1;
          if ( v32 )
            v11 = v33;
          *v11 = 0;
          if ( v32 )
          {
            v37 = v29 == v10;
            v36 = v29 - v10;
            if ( !v37 && v36 != 1 && (unsigned __int64)(2 * v36) > 2 )
              memset_0(&v31[v10 + 1], 0, 2 * v36 - 2);
          }
        }
      }
      else
      {
        *v30 = 0;
      }
    }
    else
    {
      v9 = -2147024362;
    }
  }
  else
  {
    v9 = 0;
  }
  if ( v9 < 0 )
  {
LABEL_11:
    MMNotification_Event::`scalar deleting destructor'((MMNotification_Event *)v8, 1u);
    goto LABEL_12;
  }
LABEL_42:
  v6 = (MMNotification_Event *)v8;
LABEL_12:
  if ( v9 < 0
    && WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x80000) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 29, WPP_8ed034b4a8dd37d32badf863e188f6d1_Traceguids);
  }
  if ( v6 && !PostQueuedCompletionStatus(g_WorkerEventPort, 0, (ULONG_PTR)v6, 0) )
  {
    GetLastError();
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x80000) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 30, WPP_8ed034b4a8dd37d32badf863e188f6d1_Traceguids);
    }
    MMNotification_Event::`scalar deleting destructor'(v6, 1u);
  }
  return 0;
}

```

## disassembly

```asm
0x180009e90  push    rbx
0x180009e92  push    rbp
0x180009e93  push    rsi
0x180009e94  push    rdi
0x180009e95  push    r12
0x180009e97  push    r13
0x180009e99  push    r14
0x180009e9b  push    r15
0x180009e9d  sub     rsp, 38h
0x180009ea1  mov     ebx, r8d
0x180009ea4  mov     rdi, rdx
0x180009ea7  mov     rsi, rcx
0x180009eaa  lea     r13, WPP_GLOBAL_Control
0x180009eb1  mov     rcx, cs:WPP_GLOBAL_Control
0x180009eb8  cmp     rcx, r13
0x180009ebb  jnz     loc_18000A21B
0x180009ec1  cmp     ebx, 4
0x180009ec4  jnz     loc_180009F58
0x180009eca  xor     r15d, r15d
0x180009ecd  mov     r12d, r15d
0x180009ed0  call    cs:__imp_GetProcessHeap
0x180009ed6  mov     rcx, rax; hHeap
0x180009ed9  xor     edx, edx; dwFlags
0x180009edb  mov     r8d, 58h ; 'X'; dwBytes
0x180009ee1  call    cs:__imp_HeapAlloc
0x180009ee7  mov     r14, rax
0x180009eea  mov     [rsp+78h+arg_18], rax
0x180009ef2  test    rax, rax
0x180009ef5  jnz     loc_18000A118
0x180009efb  mov     ebp, 8007000Eh
0x180009f00  jmp     short loc_180009F34
0x180009f02  lea     r9, [r8-1]
0x180009f06  test    rcx, rcx
0x180009f09  cmovnz  r9, r8
0x180009f0d  lea     rax, [rdx-2]
0x180009f11  cmovnz  rax, rdx
0x180009f15  mov     [rax], r15w
0x180009f19  jnz     loc_18000A2D0
0x180009f1f  test    ebp, ebp
0x180009f21  jns     loc_18000A109
0x180009f27  mov     edx, 1; unsigned int
0x180009f2c  mov     rcx, r14; this
0x180009f2f  call    ??_GMMNotification_Event@@UEAAPEAXI@Z; MMNotification_Event::`scalar deleting destructor'(uint)
0x180009f34  test    ebp, ebp
0x180009f36  js      loc_18000A41E
0x180009f3c  test    r12, r12
0x180009f3f  jnz     loc_18000A24C
0x180009f45  xor     eax, eax
0x180009f47  add     rsp, 38h
0x180009f4b  pop     r15
0x180009f4d  pop     r14
0x180009f4f  pop     r13
0x180009f51  pop     r12
0x180009f53  pop     rdi
0x180009f54  pop     rsi
0x180009f55  pop     rbp
0x180009f56  pop     rbx
0x180009f57  retn
0x180009f58  sub     ebx, 1
0x180009f5b  jnz     loc_18000A386
0x180009f61  xor     r15d, r15d
0x180009f64  mov     [rsp+78h+arg_18], r15
0x180009f6c  mov     rcx, cs:?g_DeviceEnumerator@@3PEAUIMMDeviceEnumerator@@EA; IMMDeviceEnumerator * g_DeviceEnumerator
0x180009f73  mov     rax, [rcx]
0x180009f76  mov     [rsp+78h+arg_18], r15
0x180009f7e  lea     r8, [rsp+78h+arg_18]
0x180009f86  mov     rdx, rdi
0x180009f89  mov     rax, [rax+28h]
0x180009f8d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009f92  mov     ebx, eax
0x180009f94  test    eax, eax
0x180009f96  js      loc_18000A334
0x180009f9c  mov     rcx, [rsp+78h+arg_18]; struct IMMDevice *
0x180009fa4  call    ?ClearVolatilePropertyStoresFromEndpoint@@YAJPEAUIMMDevice@@@Z; ClearVolatilePropertyStoresFromEndpoint(IMMDevice *)
0x180009fa9  mov     ebx, eax
0x180009fab  test    eax, eax
0x180009fad  js      loc_18000A39D
0x180009fb3  mov     rcx, [rsp+78h+arg_18]
0x180009fbb  test    rcx, rcx
0x180009fbe  jz      short loc_180009FCD
0x180009fc0  mov     rax, [rcx]
0x180009fc3  mov     rax, [rax+10h]
0x180009fc7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009fcc  nop
0x180009fcd  mov     r12, r15
0x180009fd0  call    cs:__imp_GetProcessHeap
0x180009fd6  mov     rcx, rax; hHeap
0x180009fd9  xor     edx, edx; dwFlags
0x180009fdb  mov     r8d, 58h ; 'X'; dwBytes
0x180009fe1  call    cs:__imp_HeapAlloc
0x180009fe7  mov     r14, rax
0x180009fea  mov     [rsp+78h+arg_18], rax
0x180009ff2  test    rax, rax
0x180009ff5  jz      loc_180009EFB
0x180009ffb  lea     rax, ??_7MMNotification_Event@@6B@; const MMNotification_Event::`vftable'
0x18000a002  mov     [r14], rax
0x18000a005  mov     dword ptr [r14+8], 1
0x18000a00d  mov     [r14+10h], r15
0x18000a011  mov     [r14+18h], r15
0x18000a015  mov     [r14+30h], r15
0x18000a019  mov     [r14+50h], rsi
0x18000a01d  test    r14, r14
0x18000a020  jz      loc_180009EFB
0x18000a026  test    rdi, rdi
0x18000a029  jz      loc_18000A3EA
0x18000a02f  mov     rbx, 0FFFFFFFFFFFFFFFFh
0x18000a036  inc     rbx
0x18000a039  cmp     [rdi+rbx*2], r15w
0x18000a03e  jnz     short loc_18000A036
0x18000a040  mov     [r14+10h], r15
0x18000a044  lea     rsi, [rbx+1]
0x18000a048  cmp     rsi, rbx
0x18000a04b  jb      loc_18000A111
0x18000a051  mov     eax, 2
0x18000a056  mul     rsi
0x18000a059  test    rdx, rdx
0x18000a05c  jnz     loc_18000A111
0x18000a062  mov     rcx, rax; cb
0x18000a065  call    cs:__imp_CoTaskMemAlloc
0x18000a06b  mov     r10, rax
0x18000a06e  mov     [r14+10h], rax
0x18000a072  test    rax, rax
0x18000a075  jnz     loc_18000A2C8
0x18000a07b  mov     ebp, 8007000Eh
0x18000a080  test    ebp, ebp
0x18000a082  js      loc_180009F27
0x18000a088  test    r10, r10
0x18000a08b  jz      loc_18000A3C6
0x18000a091  cmp     rsi, 7FFFFFFFh
0x18000a098  ja      loc_18000A3CF
0x18000a09e  cmp     rbx, 7FFFFFFFh
0x18000a0a5  jnb     loc_18000A3D8
0x18000a0ab  test    rsi, rsi
0x18000a0ae  jz      short loc_18000A101
0x18000a0b0  mov     rcx, rsi
0x18000a0b3  mov     rdx, r10
0x18000a0b6  mov     r8, r15
0x18000a0b9  nop     dword ptr [rax+00000000h]
0x18000a0c0  test    rbx, rbx
0x18000a0c3  jz      short loc_18000A0E4
0x18000a0c5  movzx   eax, word ptr [rdi]
0x18000a0c8  test    ax, ax
0x18000a0cb  jz      short loc_18000A0E4
0x18000a0cd  add     rdi, 2
0x18000a0d1  mov     [rdx], ax
0x18000a0d4  add     rdx, 2
0x18000a0d8  dec     rbx
0x18000a0db  inc     r8
0x18000a0de  sub     rcx, 1
0x18000a0e2  jnz     short loc_18000A0C0
0x18000a0e4  lea     r9, [r8-1]
0x18000a0e8  test    rcx, rcx
0x18000a0eb  cmovnz  r9, r8
0x18000a0ef  lea     rax, [rdx-2]
0x18000a0f3  cmovnz  rax, rdx
0x18000a0f7  mov     [rax], r15w
0x18000a0fb  jnz     loc_18000A302
0x18000a101  test    ebp, ebp
0x18000a103  js      loc_180009F27
0x18000a109  mov     r12, r14
0x18000a10c  jmp     loc_180009F34
0x18000a111  mov     ebp, 80070216h
0x18000a116  jmp     short loc_18000A101
0x18000a118  lea     rax, ??_7MMNotification_Event@@6B@; const MMNotification_Event::`vftable'
0x18000a11f  mov     [r14], rax
0x18000a122  mov     dword ptr [r14+8], 3
0x18000a12a  mov     [r14+10h], r15
0x18000a12e  mov     [r14+18h], r15
0x18000a132  mov     [r14+30h], r15
0x18000a136  mov     [r14+50h], rsi
0x18000a13a  test    r14, r14
0x18000a13d  jz      loc_180009EFB
0x18000a143  test    rdi, rdi
0x18000a146  jz      loc_18000A416
0x18000a14c  mov     rbx, 0FFFFFFFFFFFFFFFFh
0x18000a153  inc     rbx
0x18000a156  cmp     [rdi+rbx*2], r15w
0x18000a15b  jnz     short loc_18000A153
0x18000a15d  mov     [r14+10h], r15
0x18000a161  lea     rsi, [rbx+1]
0x18000a165  cmp     rsi, rbx
0x18000a168  jb      loc_18000A211
0x18000a16e  mov     eax, 2
0x18000a173  mul     rsi
0x18000a176  test    rdx, rdx
0x18000a179  jnz     loc_18000A211
0x18000a17f  mov     rcx, rax; cb
0x18000a182  call    cs:__imp_CoTaskMemAlloc
0x18000a188  mov     r10, rax
0x18000a18b  mov     [r14+10h], rax
0x18000a18f  test    rax, rax
0x18000a192  jnz     loc_18000A2C0
0x18000a198  mov     ebp, 8007000Eh
0x18000a19d  test    ebp, ebp
0x18000a19f  js      loc_180009F27
0x18000a1a5  test    r10, r10
0x18000a1a8  jz      loc_18000A3F2
0x18000a1ae  cmp     rsi, 7FFFFFFFh
0x18000a1b5  ja      loc_18000A3FB
0x18000a1bb  cmp     rbx, 7FFFFFFFh
0x18000a1c2  jnb     loc_18000A404
0x18000a1c8  test    rsi, rsi
0x18000a1cb  jz      loc_180009F1F
0x18000a1d1  mov     rcx, rsi
0x18000a1d4  mov     rdx, r10
0x18000a1d7  mov     r8, r15
0x18000a1da  nop     word ptr [rax+rax+00h]
0x18000a1e0  test    rbx, rbx
0x18000a1e3  jz      loc_180009F02
0x18000a1e9  movzx   eax, word ptr [rdi]
0x18000a1ec  test    ax, ax
0x18000a1ef  jz      loc_180009F02
0x18000a1f5  add     rdi, 2
0x18000a1f9  mov     [rdx], ax
0x18000a1fc  add     rdx, 2
0x18000a200  dec     rbx
0x18000a203  inc     r8
0x18000a206  sub     rcx, 1
0x18000a20a  jnz     short loc_18000A1E0
0x18000a20c  jmp     loc_180009F02
0x18000a211  mov     ebp, 80070216h
0x18000a216  jmp     loc_180009F1F
0x18000a21b  test    dword ptr [rcx+1Ch], 80000h
0x18000a222  jz      loc_180009EC1
0x18000a228  cmp     byte ptr [rcx+19h], 5
0x18000a22c  jb      loc_180009EC1
0x18000a232  mov     edx, 1Ch
0x18000a237  mov     [rsp+78h+var_58], ebx
0x18000a23b  mov     r9, rdi
0x18000a23e  mov     rcx, [rcx+10h]
0x18000a242  call    WPP_SF_Sd
0x18000a247  jmp     loc_180009EC1
0x18000a24c  xor     r9d, r9d; lpOverlapped
0x18000a24f  mov     r8, r12; dwCompletionKey
0x18000a252  xor     edx, edx; dwNumberOfBytesTransferred
0x18000a254  mov     rcx, cs:?g_WorkerEventPort@@3PEAXEA; CompletionPort
0x18000a25b  call    cs:__imp_PostQueuedCompletionStatus
0x18000a261  test    eax, eax
0x18000a263  jnz     loc_180009F45
0x18000a269  call    cs:__imp_GetLastError
0x18000a26f  test    eax, eax
0x18000a271  jle     short loc_18000A27B
0x18000a273  movzx   eax, ax
0x18000a276  or      eax, 80070000h
0x18000a27b  mov     rcx, cs:WPP_GLOBAL_Control
0x18000a282  cmp     rcx, r13
0x18000a285  jz      short loc_18000A2AE
0x18000a287  test    dword ptr [rcx+1Ch], 80000h
0x18000a28e  jz      short loc_18000A2AE
0x18000a290  cmp     byte ptr [rcx+19h], 2
0x18000a294  jb      short loc_18000A2AE
0x18000a296  mov     edx, 1Eh
0x18000a29b  mov     r9d, eax
0x18000a29e  lea     r8, WPP_8ed034b4a8dd37d32badf863e188f6d1_Traceguids
0x18000a2a5  mov     rcx, [rcx+10h]
0x18000a2a9  call    WPP_SF_d
0x18000a2ae  mov     edx, 1; unsigned int
0x18000a2b3  mov     rcx, r12; this
0x18000a2b6  call    ??_GMMNotification_Event@@UEAAPEAXI@Z; MMNotification_Event::`scalar deleting destructor'(uint)
0x18000a2bb  jmp     loc_180009F45
0x18000a2c0  mov     ebp, r15d
0x18000a2c3  jmp     loc_18000A19D
0x18000a2c8  mov     ebp, r15d
0x18000a2cb  jmp     loc_18000A080
0x18000a2d0  sub     rsi, r9
0x18000a2d3  cmp     rsi, 1
0x18000a2d7  jbe     loc_180009F1F
0x18000a2dd  lea     r8, [rsi+rsi]
0x18000a2e1  cmp     r8, 2
0x18000a2e5  jbe     loc_180009F1F
0x18000a2eb  add     r8, 0FFFFFFFFFFFFFFFEh; Size
0x18000a2ef  inc     r9
0x18000a2f2  lea     rcx, [r10+r9*2]; void *
0x18000a2f6  xor     edx, edx; Val
0x18000a2f8  call    memset_0
0x18000a2fd  jmp     loc_180009F1F
0x18000a302  sub     rsi, r9
0x18000a305  cmp     rsi, 1
0x18000a309  jbe     loc_18000A101
0x18000a30f  lea     r8, [rsi+rsi]
0x18000a313  cmp     r8, 2
0x18000a317  jbe     loc_18000A101
0x18000a31d  add     r8, 0FFFFFFFFFFFFFFFEh; Size
0x18000a321  inc     r9
0x18000a324  lea     rcx, [r10+r9*2]; void *
0x18000a328  xor     edx, edx; Val
0x18000a32a  call    memset_0
0x18000a32f  jmp     loc_18000A101
0x18000a334  mov     rcx, [rsp+78h]; this
0x18000a339  mov     r9d, eax; char *
0x18000a33c  lea     r8, aAvcoreAudiocor_1; "avcore\\audiocore\\server\\audioendpoin"...
0x18000a343  mov     edx, 557h; void *
0x18000a348  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000a34d  nop
0x18000a34e  mov     rcx, [rsp+78h+arg_18]
0x18000a356  test    rcx, rcx
0x18000a359  jz      short loc_18000A368
0x18000a35b  mov     rax, [rcx]
0x18000a35e  mov     rax, [rax+10h]
0x18000a362  call    _guard_dispatch_icall$thunk$10345483385596137414
  ... truncated ...
```
