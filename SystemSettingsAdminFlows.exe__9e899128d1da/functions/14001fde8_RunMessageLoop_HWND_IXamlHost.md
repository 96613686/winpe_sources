# RunMessageLoop(HWND__ *,IXamlHost *)

- ea: `0x14001fde8`
- end: `0x140020117`
- name: `?RunMessageLoop@@YAXPEAUHWND__@@PEAUIXamlHost@@@Z`
- size: `815`
- prototype: `void __fastcall(HWND hWnd, struct IXamlHost *)`
- caller_count: `2`
- callee_count: `6`
- tags: `authz_impersonation, registry_config, installer_update, broker_com_uri`

## callers

- `0x1400233a0`
- `0x140077330`

## callees

- `0x140009a68`
- `0x14000e624`
- `0x14001a2a0`
- `0x14001fde8`
- `0x14002dd70`
- `0x14007d010`

## import_xrefs

- `KERNEL32!CreateEventW` at `0x14001fec3`
- `KERNEL32!CreateEventW` at `0x14001fec3`
- `KERNEL32!OpenProcess` at `0x14001ff14`
- `KERNEL32!OpenProcess` at `0x14001ff14`
- `KERNEL32!CloseHandle` at `0x1400200d1`
- `KERNEL32!CloseHandle` at `0x1400200e5`
- `KERNEL32!CloseHandle` at `0x1400200d1`
- `KERNEL32!CloseHandle` at `0x1400200e5`
- `KERNEL32!TlsGetValue` at `0x14001fe10`
- `KERNEL32!TlsGetValue` at `0x14001fe10`
- `KERNEL32!ResetEvent` at `0x14001fee7`
- `KERNEL32!ResetEvent` at `0x14001fff0`
- `KERNEL32!ResetEvent` at `0x14001fee7`
- `KERNEL32!ResetEvent` at `0x14001fff0`
- `KERNEL32!TlsSetValue` at `0x14001fe3e`
- `KERNEL32!TlsSetValue` at `0x14001fe3e`
- `USER32!PeekMessageW` at `0x14001ff7f`
- `USER32!PeekMessageW` at `0x14001ffc1`
- `USER32!PeekMessageW` at `0x14001ff7f`
- `USER32!PeekMessageW` at `0x14001ffc1`
- `USER32!MsgWaitForMultipleObjectsEx` at `0x14001ff52`
- `USER32!MsgWaitForMultipleObjectsEx` at `0x14001ff52`
- `USER32!TranslateMessage` at `0x14001ff97`
- `USER32!TranslateMessage` at `0x14001ff97`
- `USER32!DispatchMessageW` at `0x14001ffa1`
- `USER32!DispatchMessageW` at `0x14001ffa1`
- `USER32!GetWindowThreadProcessId` at `0x14001ff03`
- `USER32!GetWindowThreadProcessId` at `0x14001ff03`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
void __fastcall RunMessageLoop(HWND hWnd, struct IXamlHost *a2)
{
  __int64 *Value; // rax
  __int64 *p_TlsValue; // rdi
  DWORD v6; // esi
  unsigned int v7; // ecx
  __int64 v8; // rcx
  char *EventW; // rax
  char *v10; // r14
  int v11; // r12d
  HANDLE v12; // rax
  int v13; // r15d
  char v14; // bl
  DWORD v15; // eax
  char *v16; // rbx
  unsigned int v17; // edx
  __int64 v18; // r15
  __int64 v19; // [rsp+30h] [rbp-59h] BYREF
  DWORD v20; // [rsp+38h] [rbp-51h] BYREF
  __int64 TlsValue; // [rsp+40h] [rbp-49h] BYREF
  __int64 (__fastcall ***v22)(_QWORD, GUID *, __int64); // [rsp+48h] [rbp-41h] BYREF
  __int64 *v23; // [rsp+50h] [rbp-39h]
  HANDLE hObject; // [rsp+58h] [rbp-31h]
  HANDLE pHandles[2]; // [rsp+60h] [rbp-29h] BYREF
  tagMSG Msg; // [rsp+70h] [rbp-19h] BYREF
  char *v27; // [rsp+A0h] [rbp+17h]
  char v28; // [rsp+100h] [rbp+77h]
  DWORD dwProcessId; // [rsp+108h] [rbp+7Fh] BYREF

  Value = (__int64 *)TlsGetValue(__g_tracingTlsSlot);
  p_TlsValue = Value;
  v20 = -1;
  TlsValue = 0;
  if ( Value )
  {
    v23 = Value;
  }
  else
  {
    p_TlsValue = &TlsValue;
    v20 = __g_tracingTlsSlot;
    TlsSetValue(__g_tracingTlsSlot, &TlsValue);
    v23 = &TlsValue;
  }
  v6 = 1;
  ++*(_DWORD *)p_TlsValue;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *((char *)WPP_GLOBAL_Control + 28) < 0 )
  {
    v7 = 5 * *(_DWORD *)p_TlsValue;
    if ( v7 > 0x1E1 )
      v8 = 0;
    else
      v8 = 479LL - v7;
    WPP_SF_s(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      12,
      &WPP_efafaf3e289e3856a10987a4bac777a3_Traceguids,
      &asc_1400849C0[v8]);
  }
  *(_OWORD *)pHandles = 0;
  EventW = (char *)CreateEventW(0, 1, 0, L"Local\\Windows.SystemSettings.AdminFlowResizeEvent");
  v10 = EventW;
  v27 = EventW;
  v11 = -1;
  if ( EventW )
  {
    pHandles[0] = EventW;
    LODWORD(v19) = 0;
    ResetEvent(EventW);
  }
  else
  {
    v6 = 0;
    LODWORD(v19) = -1;
  }
  dwProcessId = 0;
  GetWindowThreadProcessId(hWnd, &dwProcessId);
  v12 = OpenProcess(0x100000u, 0, dwProcessId);
  hObject = v12;
  if ( v12 )
  {
    pHandles[v6] = v12;
    v11 = v6++;
  }
  v28 = 1;
  v13 = v19;
  v14 = 1;
  do
  {
    v15 = MsgWaitForMultipleObjectsEx(v6, pHandles, 0xFFFFFFFF, 0x1CFFu, 6u);
    if ( v15 == v6 )
    {
      memset(&Msg, 0, sizeof(Msg));
      if ( PeekMessageW(&Msg, 0, 0, 0, 1u) )
      {
        do
        {
          if ( Msg.message == 18 )
          {
            v28 = 0;
          }
          else
          {
            TranslateMessage(&Msg);
            DispatchMessageW(&Msg);
          }
        }
        while ( PeekMessageW(&Msg, 0, 0, 0, 1u) );
        v14 = v28;
      }
    }
    else if ( v13 >= 0 && v15 == v13 )
    {
      (*(void (__fastcall **)(struct IXamlHost *))(*(_QWORD *)a2 + 80LL))(a2);
      ResetEvent(v10);
    }
    else if ( v11 >= 0 && v15 == v11 )
    {
      v22 = (__int64 (__fastcall ***)(_QWORD, GUID *, __int64))a2;
      if ( a2 )
        (*(void (__fastcall **)(struct IXamlHost *))(*(_QWORD *)a2 + 8LL))(a2);
      v19 = 0;
      if ( (int)Microsoft::WRL::ComPtr<IXamlHost>::As<SystemSettings::XamlHost::IXamlHostHelper>(&v22, (__int64)&v19) >= 0 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v19 + 56LL))(v19);
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v19);
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v22);
    }
    else if ( v15 != 192 )
    {
      break;
    }
  }
  while ( v14 );
  v16 = (char *)hObject;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *((char *)WPP_GLOBAL_Control + 28) < 0 )
  {
    v17 = 5 * *(_DWORD *)p_TlsValue;
    if ( v17 > 0x1E1 )
      v18 = 0;
    else
      v18 = 479LL - v17;
    WPP_SF_s(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      13,
      &WPP_efafaf3e289e3856a10987a4bac777a3_Traceguids,
      &asc_1400849C0[v18]);
  }
  if ( (unsigned __int64)(v16 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
    CloseHandle(v16);
  if ( (unsigned __int64)(v10 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
    CloseHandle(v10);
  if ( p_TlsValue )
    --*(_DWORD *)p_TlsValue;
  TracingInternal::AutoTlsPtr<TracingInternal::TracingContext>::~AutoTlsPtr<TracingInternal::TracingContext>(&v20);
}

```

## disassembly

```asm
0x14001fde8  mov     [rsp-8+arg_0], rbx
0x14001fded  push    rbp
0x14001fdee  push    rsi
0x14001fdef  push    rdi
0x14001fdf0  push    r12
0x14001fdf2  push    r13
0x14001fdf4  push    r14
0x14001fdf6  push    r15
0x14001fdf8  lea     rbp, [rsp-27h]
0x14001fdfd  sub     rsp, 0B0h
0x14001fe04  mov     r13, rdx
0x14001fe07  mov     rbx, rcx
0x14001fe0a  mov     ecx, cs:?__g_tracingTlsSlot@@3KA; dwTlsIndex
0x14001fe10  call    cs:__imp_TlsGetValue
0x14001fe16  mov     rdi, rax
0x14001fe19  mov     [rbp+57h+var_A8], 0FFFFFFFFh
0x14001fe20  mov     [rbp+57h+TlsValue], 0
0x14001fe28  test    rax, rax
0x14001fe2b  jnz     short loc_14001FE4A
0x14001fe2d  lea     rdi, [rbp+57h+TlsValue]
0x14001fe31  mov     ecx, cs:?__g_tracingTlsSlot@@3KA; dwTlsIndex
0x14001fe37  mov     [rbp+57h+var_A8], ecx
0x14001fe3a  lea     rdx, [rbp+57h+TlsValue]; lpTlsValue
0x14001fe3e  call    cs:__imp_TlsSetValue
0x14001fe44  mov     [rbp+57h+var_90], rdi
0x14001fe48  jmp     short loc_14001FE4E
0x14001fe4a  mov     [rbp+57h+var_90], rax
0x14001fe4e  mov     esi, 1
0x14001fe53  add     [rdi], esi
0x14001fe55  lea     rax, WPP_GLOBAL_Control
0x14001fe5c  mov     r15d, 1DFh
0x14001fe62  lea     rdx, asc_1400849C0; "                                       "...
0x14001fe69  mov     r10, cs:WPP_GLOBAL_Control
0x14001fe70  cmp     r10, rax
0x14001fe73  jz      short loc_14001FEAE
0x14001fe75  test    byte ptr [r10+1Ch], 80h
0x14001fe7a  jz      short loc_14001FEAE
0x14001fe7c  mov     eax, [rdi]
0x14001fe7e  lea     ecx, [rax+rax*4]
0x14001fe81  cmp     ecx, 1E1h
0x14001fe87  ja      short loc_14001FE93
0x14001fe89  mov     eax, ecx
0x14001fe8b  mov     ecx, r15d
0x14001fe8e  sub     rcx, rax
0x14001fe91  jmp     short loc_14001FE95
0x14001fe93  xor     ecx, ecx
0x14001fe95  lea     r9, [rcx+rdx]
0x14001fe99  mov     edx, 0Ch
0x14001fe9e  lea     r8, WPP_efafaf3e289e3856a10987a4bac777a3_Traceguids
0x14001fea5  mov     rcx, [r10+10h]
0x14001fea9  call    WPP_SF_s
0x14001feae  xorps   xmm0, xmm0
0x14001feb1  movups  xmmword ptr [rbp+57h+pHandles], xmm0
0x14001feb5  lea     r9, Name; "Local\\Windows.SystemSettings.AdminFlow"...
0x14001febc  xor     r8d, r8d; bInitialState
0x14001febf  mov     edx, esi; bManualReset
0x14001fec1  xor     ecx, ecx; lpEventAttributes
0x14001fec3  call    cs:__imp_CreateEventW
0x14001fec9  mov     r14, rax
0x14001fecc  mov     [rbp+57h+var_40], rax
0x14001fed0  or      r12d, 0FFFFFFFFh
0x14001fed4  test    rax, rax
0x14001fed7  jz      short loc_14001FEEF
0x14001fed9  mov     [rbp+57h+pHandles], rax
0x14001fedd  mov     dword ptr [rbp+57h+var_B0], 0
0x14001fee4  mov     rcx, rax; hEvent
0x14001fee7  call    cs:__imp_ResetEvent
0x14001feed  jmp     short loc_14001FEF5
0x14001feef  xor     esi, esi
0x14001fef1  mov     dword ptr [rbp+57h+var_B0], r12d
0x14001fef5  mov     [rbp+57h+dwProcessId], 0
0x14001fefc  lea     rdx, [rbp+57h+dwProcessId]; lpdwProcessId
0x14001ff00  mov     rcx, rbx; hWnd
0x14001ff03  call    cs:__imp_GetWindowThreadProcessId
0x14001ff09  mov     r8d, [rbp+57h+dwProcessId]; dwProcessId
0x14001ff0d  xor     edx, edx; bInheritHandle
0x14001ff0f  mov     ecx, 100000h; dwDesiredAccess
0x14001ff14  call    cs:__imp_OpenProcess
0x14001ff1a  mov     [rbp+57h+hObject], rax
0x14001ff1e  test    rax, rax
0x14001ff21  jz      short loc_14001FF2F
0x14001ff23  mov     ecx, esi
0x14001ff25  mov     [rbp+rcx*8+57h+pHandles], rax
0x14001ff2a  mov     r12d, esi
0x14001ff2d  inc     esi
0x14001ff2f  mov     [rbp+57h+arg_10], 1
0x14001ff33  mov     r15d, dword ptr [rbp+57h+var_B0]
0x14001ff37  mov     bl, [rbp+57h+arg_10]
0x14001ff3a  mov     [rsp+0E0h+dwFlags], 6; dwFlags
0x14001ff42  mov     r9d, 1CFFh; dwWakeMask
0x14001ff48  or      r8d, 0FFFFFFFFh; dwMilliseconds
0x14001ff4c  lea     rdx, [rbp+57h+pHandles]; pHandles
0x14001ff50  mov     ecx, esi; nCount
0x14001ff52  call    cs:__imp_MsgWaitForMultipleObjectsEx
0x14001ff58  cmp     eax, esi
0x14001ff5a  jnz     short loc_14001FFD3
0x14001ff5c  xorps   xmm0, xmm0
0x14001ff5f  movups  xmmword ptr [rbp+57h+Msg.hwnd], xmm0
0x14001ff63  movups  xmmword ptr [rbp+57h+Msg.wParam], xmm0
0x14001ff67  movups  xmmword ptr [rbp+57h+Msg.time], xmm0
0x14001ff6b  mov     [rsp+0E0h+dwFlags], 1; wRemoveMsg
0x14001ff73  xor     r9d, r9d; wMsgFilterMax
0x14001ff76  xor     r8d, r8d; wMsgFilterMin
0x14001ff79  xor     edx, edx; hWnd
0x14001ff7b  lea     rcx, [rbp+57h+Msg]; lpMsg
0x14001ff7f  call    cs:__imp_PeekMessageW
0x14001ff85  test    eax, eax
0x14001ff87  jz      loc_140020062
0x14001ff8d  cmp     [rbp+57h+Msg.message], 12h
0x14001ff91  jz      short loc_14001FFA9
0x14001ff93  lea     rcx, [rbp+57h+Msg]; lpMsg
0x14001ff97  call    cs:__imp_TranslateMessage
0x14001ff9d  lea     rcx, [rbp+57h+Msg]; lpMsg
0x14001ffa1  call    cs:__imp_DispatchMessageW
0x14001ffa7  jmp     short loc_14001FFAD
0x14001ffa9  mov     [rbp+57h+arg_10], 0
0x14001ffad  mov     [rsp+0E0h+dwFlags], 1; wRemoveMsg
0x14001ffb5  xor     r9d, r9d; wMsgFilterMax
0x14001ffb8  xor     r8d, r8d; wMsgFilterMin
0x14001ffbb  xor     edx, edx; hWnd
0x14001ffbd  lea     rcx, [rbp+57h+Msg]; lpMsg
0x14001ffc1  call    cs:__imp_PeekMessageW
0x14001ffc7  test    eax, eax
0x14001ffc9  jnz     short loc_14001FF8D
0x14001ffcb  mov     bl, [rbp+57h+arg_10]
0x14001ffce  jmp     loc_140020062
0x14001ffd3  test    r15d, r15d
0x14001ffd6  js      short loc_14001FFF8
0x14001ffd8  cmp     eax, r15d
0x14001ffdb  jnz     short loc_14001FFF8
0x14001ffdd  mov     rax, [r13+0]
0x14001ffe1  mov     rcx, r13
0x14001ffe4  mov     rax, [rax+50h]
0x14001ffe8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001ffed  mov     rcx, r14; hEvent
0x14001fff0  call    cs:__imp_ResetEvent
0x14001fff6  jmp     short loc_140020062
0x14001fff8  test    r12d, r12d
0x14001fffb  js      short loc_14002005B
0x14001fffd  cmp     eax, r12d
0x140020000  jnz     short loc_14002005B
0x140020002  mov     [rbp+57h+var_98], r13
0x140020006  test    r13, r13
0x140020009  jz      short loc_14002001C
0x14002000b  mov     rax, [r13+0]
0x14002000f  mov     rcx, r13
0x140020012  mov     rax, [rax+8]
0x140020016  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14002001b  nop
0x14002001c  mov     [rbp+57h+var_B0], 0
0x140020024  lea     rdx, [rbp+57h+var_B0]
0x140020028  lea     rcx, [rbp+57h+var_98]
0x14002002c  call    ??$As@UIXamlHostHelper@XamlHost@SystemSettings@@@?$ComPtr@UIXamlHost@@@WRL@Microsoft@@QEBAJV?$ComPtrRef@V?$ComPtr@UIXamlHostHelper@XamlHost@SystemSettings@@@WRL@Microsoft@@@Details@12@@Z; Microsoft::WRL::ComPtr<IXamlHost>::As<SystemSettings::XamlHost::IXamlHostHelper>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<SystemSettings::XamlHost::IXamlHostHelper>>)
0x140020031  test    eax, eax
0x140020033  js      short loc_140020046
0x140020035  mov     rcx, [rbp+57h+var_B0]
0x140020039  mov     rax, [rcx]
0x14002003c  mov     rax, [rax+38h]
0x140020040  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140020045  nop
0x140020046  lea     rcx, [rbp+57h+var_B0]
0x14002004a  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x14002004f  nop
0x140020050  lea     rcx, [rbp+57h+var_98]
0x140020054  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x140020059  jmp     short loc_140020062
0x14002005b  cmp     eax, 0C0h
0x140020060  jnz     short loc_14002006A
0x140020062  test    bl, bl
0x140020064  jnz     loc_14001FF3A
0x14002006a  mov     rcx, cs:WPP_GLOBAL_Control
0x140020071  lea     rax, WPP_GLOBAL_Control
0x140020078  cmp     rcx, rax
0x14002007b  mov     rbx, [rbp+57h+hObject]
0x14002007f  mov     r15d, 1DFh
0x140020085  jz      short loc_1400200C4
0x140020087  test    byte ptr [rcx+1Ch], 80h
0x14002008b  jz      short loc_1400200C4
0x14002008d  mov     eax, [rdi]
0x14002008f  lea     edx, [rax+rax*4]
0x140020092  cmp     edx, 1E1h
0x140020098  ja      short loc_1400200A1
0x14002009a  mov     eax, edx
0x14002009c  sub     r15, rax
0x14002009f  jmp     short loc_1400200A4
0x1400200a1  xor     r15d, r15d
0x1400200a4  lea     r9, asc_1400849C0; "                                       "...
0x1400200ab  add     r9, r15
0x1400200ae  mov     edx, 0Dh
0x1400200b3  lea     r8, WPP_efafaf3e289e3856a10987a4bac777a3_Traceguids
0x1400200ba  mov     rcx, [rcx+10h]
0x1400200be  call    WPP_SF_s
0x1400200c3  nop
0x1400200c4  lea     rax, [rbx-1]
0x1400200c8  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1400200cc  ja      short loc_1400200D8
0x1400200ce  mov     rcx, rbx; hObject
0x1400200d1  call    cs:__imp_CloseHandle
0x1400200d7  nop
0x1400200d8  lea     rax, [r14-1]
0x1400200dc  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1400200e0  ja      short loc_1400200EC
0x1400200e2  mov     rcx, r14; hObject
0x1400200e5  call    cs:__imp_CloseHandle
0x1400200eb  nop
0x1400200ec  test    rdi, rdi
0x1400200ef  jz      short loc_1400200F3
0x1400200f1  dec     dword ptr [rdi]
0x1400200f3  lea     rcx, [rbp+57h+var_A8]
0x1400200f7  call    ??1?$AutoTlsPtr@UTracingContext@TracingInternal@@@TracingInternal@@QEAA@XZ; TracingInternal::AutoTlsPtr<TracingInternal::TracingContext>::~AutoTlsPtr<TracingInternal::TracingContext>(void)
0x1400200fc  mov     rbx, [rsp+0E0h+arg_0]
0x140020104  add     rsp, 0B0h
0x14002010b  pop     r15
0x14002010d  pop     r14
0x14002010f  pop     r13
0x140020111  pop     r12
0x140020113  pop     rdi
0x140020114  pop     rsi
0x140020115  pop     rbp
0x140020116  retn
```
