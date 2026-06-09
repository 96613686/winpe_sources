# Instance::InitInstance(bool)

- ea: `0x18004a1a4`
- end: `0x18004a836`
- name: `?InitInstance@Instance@@AEAAJ_N@Z`
- size: `1682`
- prototype: `__int64 __fastcall(Instance *__hidden this, bool)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting, service_task, installer_update`

## callers

- `0x18004a840`

## callees

- `0x180001304`
- `0x1800495e4`
- `0x18004a1a4`

## import_xrefs

- `ntdll!RtlAllocateHeap` at `0x18004a251`
- `ntdll!RtlAllocateHeap` at `0x18004a2a5`
- `ntdll!RtlAllocateHeap` at `0x18004a2ff`
- `ntdll!RtlAllocateHeap` at `0x18004a355`
- `ntdll!RtlAllocateHeap` at `0x18004a491`
- `ntdll!RtlAllocateHeap` at `0x18004a521`
- `ntdll!RtlAllocateHeap` at `0x18004a251`
- `ntdll!RtlAllocateHeap` at `0x18004a2a5`
- `ntdll!RtlAllocateHeap` at `0x18004a2ff`
- `ntdll!RtlAllocateHeap` at `0x18004a355`
- `ntdll!RtlAllocateHeap` at `0x18004a491`
- `ntdll!RtlAllocateHeap` at `0x18004a521`
- `ntdll!RtlQueryWnfStateData` at `0x18004a6b9`
- `ntdll!RtlQueryWnfStateData` at `0x18004a6b9`
- `ntdll!RtlSubscribeWnfStateChangeNotification` at `0x18004a6f5`
- `ntdll!RtlSubscribeWnfStateChangeNotification` at `0x18004a6f5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004a394`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004a394`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18004a1c6`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18004a1c6`
- `ext-ms-win-ntuser-windowclass-l1-1-0!RegisterClassExW` at `0x18004a21a`
- `ext-ms-win-ntuser-windowclass-l1-1-0!RegisterClassExW` at `0x18004a21a`

## string_xrefs

- `0x18004a1f6`: `GameInputServiceWindow`

## pseudocode

```c
__int64 __fastcall Instance::InitInstance(struct MessageWindow **this, char a2)
{
  ATOM v4; // ax
  _QWORD *Heap; // rax
  int v6; // r8d
  int v7; // r9d
  struct _PEB *v8; // rcx
  _BYTE *v9; // rax
  struct _PEB *v10; // rcx
  _QWORD *v11; // rax
  struct _PEB *v12; // rcx
  _QWORD *v13; // rax
  int v14; // r8d
  int v15; // r9d
  signed int LastError; // eax
  unsigned int MessageOnlyWindow; // edi
  char *v18; // rdx
  const char *v19; // rcx
  struct MessageWindow *v21; // rax
  _QWORD *v22; // rax
  int *v23; // rdx
  _QWORD v24[2]; // [rsp+40h] [rbp-29h] BYREF
  WNDCLASSEXW v25; // [rsp+50h] [rbp-19h] BYREF
  unsigned int v26; // [rsp+D0h] [rbp+67h] BYREF
  int v27; // [rsp+E0h] [rbp+77h] BYREF
  int v28; // [rsp+E8h] [rbp+7Fh] BYREF

  MessageWindow::s_instance = (struct Instance *)this;
  *(_QWORD *)&v25.cbSize = 80;
  MessageWindow::s_moduleHandle = GetModuleHandleW(0);
  v25.hInstance = MessageWindow::s_moduleHandle;
  v25.lpfnWndProc = (WNDPROC)MessageWindow::WinProcCallbackThunk;
  v25.lpszClassName = L"GameInputServiceWindow";
  *(_QWORD *)&v25.cbClsExtra = 0;
  memset(&v25.hIcon, 0, 32);
  v25.hIconSm = 0;
  v4 = RegisterClassExW(&v25);
  if ( v4 )
  {
    MessageWindow::s_wndClassAtom = v4;
  }
  else
  {
    LastError = GetLastError();
    MessageOnlyWindow = LastError;
    if ( LastError > 0 )
      MessageOnlyWindow = (unsigned __int16)LastError | 0x80070000;
    if ( (MessageOnlyWindow & 0x80000000) != 0 )
    {
      if ( (unsigned int)dword_180069000 <= 2
        || (qword_180069010 & 0x400) == 0
        || (qword_180069018 & 0x400) != qword_180069018 )
      {
        return MessageOnlyWindow;
      }
      v28 = 265;
      v18 = byte_180064333;
LABEL_15:
      v19 = "onecore\\xbox\\gameinput\\router\\Instance.cpp";
      v24[0] = "onecore\\xbox\\gameinput\\router\\Instance.cpp";
LABEL_16:
      v27 = MessageOnlyWindow;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_GameInputEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        (_DWORD)v19,
        (_DWORD)v18,
        v14,
        v15,
        (__int64)v24,
        (__int64)&v28,
        (__int64)&v27);
      return MessageOnlyWindow;
    }
  }
  this[9] = 0;
  Heap = RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, 0x30u);
  if ( !Heap )
  {
    FocusWatcher::s_singleton = 0;
    if ( (unsigned int)dword_180069000 <= 2
      || (qword_180069010 & 0x400) == 0
      || (qword_180069018 & 0x400) != qword_180069018 )
    {
      return 2147500037LL;
    }
    v28 = 269;
    v23 = &dword_1800641B4;
    goto LABEL_63;
  }
  Heap[1] = this;
  *Heap = &FocusWatcher::`vftable';
  *((_DWORD *)Heap + 4) = 0;
  Heap[3] = 0;
  Heap[4] = 0;
  Heap[5] = 0;
  this[9] = (struct MessageWindow *)Heap;
  this[10] = 0;
  v8 = NtCurrentPeb();
  FocusWatcher::s_singleton = (FocusWatcher *)Heap;
  v9 = RtlAllocateHeap(v8->ProcessHeap, 0, 0x30u);
  if ( !v9 )
  {
    RawInputWatcher::s_singleton = 0;
    if ( (unsigned int)dword_180069000 <= 2
      || (qword_180069010 & 0x400) == 0
      || (qword_180069018 & 0x400) != qword_180069018 )
    {
      return 2147500037LL;
    }
    v28 = 272;
    v23 = &dword_18006422C;
    goto LABEL_63;
  }
  v9[16] = a2;
  *(_QWORD *)v9 = &RawInputWatcher::`vftable';
  *((_QWORD *)v9 + 1) = this;
  *((_DWORD *)v9 + 10) = 0;
  *((_QWORD *)v9 + 4) = v9 + 24;
  *((_QWORD *)v9 + 3) = v9 + 24;
  this[10] = (struct MessageWindow *)v9;
  this[11] = 0;
  v10 = NtCurrentPeb();
  RawInputWatcher::s_singleton = (struct RawInputWatcher *)v9;
  v11 = RtlAllocateHeap(v10->ProcessHeap, 0, 0x38u);
  if ( !v11 )
  {
    KeyboardLayoutWatcher::s_singleton = 0;
    if ( (unsigned int)dword_180069000 <= 2
      || (qword_180069010 & 0x400) == 0
      || (qword_180069018 & 0x400) != qword_180069018 )
    {
      return 2147500037LL;
    }
    v28 = 275;
    v23 = (int *)&unk_1800643C0;
LABEL_63:
    v27 = -2147467259;
    v24[0] = "onecore\\xbox\\gameinput\\router\\Instance.cpp";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_GameInputEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
      (unsigned int)"onecore\\xbox\\gameinput\\router\\Instance.cpp",
      (_DWORD)v23,
      v6,
      v7,
      (__int64)v24,
      (__int64)&v28,
      (__int64)&v27);
    return 2147500037LL;
  }
  v11[2] = 0;
  *v11 = &KeyboardLayoutWatcher::`vftable';
  v11[3] = 0;
  v11[1] = this;
  v11[4] = 0;
  v11[5] = 0;
  *((_BYTE *)v11 + 48) = 0;
  this[11] = (struct MessageWindow *)v11;
  v12 = NtCurrentPeb();
  KeyboardLayoutWatcher::s_singleton = (struct KeyboardLayoutWatcher *)v11;
  v13 = RtlAllocateHeap(v12->ProcessHeap, 0, 0x38u);
  if ( v13 )
  {
    v13[1] = this;
    *v13 = &PnpInterfaceWatcher::`vftable';
    *((_DWORD *)v13 + 10) = 0;
    v13[4] = v13 + 3;
    v13[3] = v13 + 3;
    v13[6] = 0;
    v13[2] = 0;
  }
  else
  {
    v13 = 0;
  }
  this[13] = (struct MessageWindow *)v13;
  MessageOnlyWindow = -2147024882;
  if ( !v13 )
  {
    if ( (unsigned int)dword_180069000 <= 2
      || (qword_180069010 & 0x400) == 0
      || (qword_180069018 & 0x400) != qword_180069018 )
    {
      return MessageOnlyWindow;
    }
    v28 = 278;
    v18 = byte_180064669;
    goto LABEL_15;
  }
  this[14] = (struct MessageWindow *)v13;
  v21 = (struct MessageWindow *)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, 0x18u);
  if ( v21 )
  {
    *((_QWORD *)v21 + 1) = this;
    *(_QWORD *)v21 = &PnpInstanceWatcher::`vftable';
    *((_QWORD *)v21 + 2) = 0;
  }
  else
  {
    v21 = 0;
  }
  this[15] = v21;
  if ( !v21 )
  {
    if ( (unsigned int)dword_180069000 <= 2
      || (qword_180069010 & 0x400) == 0
      || (qword_180069018 & 0x400) != qword_180069018 )
    {
      return MessageOnlyWindow;
    }
    v28 = 282;
    v18 = byte_1800640D9;
    goto LABEL_15;
  }
  v22 = RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, 0x38u);
  if ( v22 )
  {
    v22[1] = this;
    *v22 = &PnpHandleWatcher::`vftable';
    *((_DWORD *)v22 + 10) = 0;
    v22[4] = v22 + 3;
    v22[3] = v22 + 3;
    v22[6] = 0;
    v22[2] = 0;
  }
  else
  {
    v22 = 0;
  }
  this[12] = (struct MessageWindow *)v22;
  if ( !v22 )
  {
    if ( (unsigned int)dword_180069000 <= 2
      || (qword_180069010 & 0x400) == 0
      || (qword_180069018 & 0x400) != qword_180069018 )
    {
      return MessageOnlyWindow;
    }
    v28 = 285;
    v24[0] = "onecore\\xbox\\gameinput\\router\\Instance.cpp";
    v18 = byte_1800646B9;
    v19 = (const char *)v24;
    goto LABEL_16;
  }
  this[16] = (struct MessageWindow *)v22;
  MessageOnlyWindow = MessageWindow::CreateMessageOnlyWindow(1, this + 7);
  if ( (MessageOnlyWindow & 0x80000000) != 0 )
  {
    if ( (unsigned int)dword_180069000 <= 2 )
      return MessageOnlyWindow;
    v14 = qword_180069018;
    if ( (qword_180069010 & 0x400) == 0 || (qword_180069018 & 0x400) != qword_180069018 )
      return MessageOnlyWindow;
    v28 = 290;
    v18 = byte_180064061;
    goto LABEL_15;
  }
  MessageOnlyWindow = MessageWindow::CreateMessageOnlyWindow(0, this + 8);
  if ( (MessageOnlyWindow & 0x80000000) != 0 )
  {
    if ( (unsigned int)dword_180069000 <= 2 )
      return MessageOnlyWindow;
    v14 = qword_180069018;
    if ( (qword_180069010 & 0x400) == 0 || (qword_180069018 & 0x400) != qword_180069018 )
      return MessageOnlyWindow;
    v28 = 293;
    v18 = &byte_180063FE7;
    goto LABEL_15;
  }
  v26 = 0;
  RtlQueryWnfStateData(&v26, WNF_SHEL_GAMECONTROLLER_FOCUS_INFO, Instance::OnFocusOverrideWnfChanged, this, 0);
  RtlSubscribeWnfStateChangeNotification(
    this + 18,
    WNF_SHEL_GAMECONTROLLER_FOCUS_INFO,
    v26,
    Instance::OnFocusOverrideWnfChanged,
    this,
    0,
    0,
    1);
  return 0;
}

```

## disassembly

```asm
0x18004a1a4  push    rbp
0x18004a1a6  push    rbx
0x18004a1a7  push    rsi
0x18004a1a8  push    rdi
0x18004a1a9  push    r14
0x18004a1ab  lea     rbp, [rsp-37h]
0x18004a1b0  sub     rsp, 0A0h
0x18004a1b7  mov     rbx, rcx
0x18004a1ba  mov     cs:?s_instance@MessageWindow@@0PEAVInstance@@EA, rcx; Instance * MessageWindow::s_instance
0x18004a1c1  xor     ecx, ecx; lpModuleName
0x18004a1c3  mov     sil, dl
0x18004a1c6  call    cs:__imp_GetModuleHandleW
0x18004a1cd  nop     dword ptr [rax+rax+00h]
0x18004a1d2  lea     rcx, ?WinProcCallbackThunk@MessageWindow@@CA_JQEAUHWND__@@I_K_J@Z; MessageWindow::WinProcCallbackThunk(HWND__ * const,uint,unsigned __int64,__int64)
0x18004a1d9  mov     qword ptr [rbp+57h+var_70.cbSize], 50h ; 'P'
0x18004a1e1  mov     cs:?s_moduleHandle@MessageWindow@@0PEAUHINSTANCE__@@EA, rax; HINSTANCE__ * MessageWindow::s_moduleHandle
0x18004a1e8  xor     r14d, r14d
0x18004a1eb  mov     [rbp+57h+var_70.hInstance], rax
0x18004a1ef  xorps   xmm0, xmm0
0x18004a1f2  mov     [rbp+57h+var_70.lpfnWndProc], rcx
0x18004a1f6  lea     rax, ClassName; "GameInputServiceWindow"
0x18004a1fd  xorps   xmm1, xmm1
0x18004a200  mov     [rbp+57h+var_70.lpszClassName], rax
0x18004a204  lea     rcx, [rbp+57h+var_70]; WNDCLASSEXW *
0x18004a208  mov     qword ptr [rbp+57h+var_70.cbClsExtra], r14
0x18004a20c  movdqa  xmmword ptr [rbp+57h+var_70.hIcon], xmm0
0x18004a211  movdqa  xmmword ptr [rbp+57h+var_70.hbrBackground], xmm1
0x18004a216  mov     [rbp+57h+var_70.hIconSm], r14
0x18004a21a  call    cs:__imp_RegisterClassExW
0x18004a221  nop     dword ptr [rax+rax+00h]
0x18004a226  test    ax, ax
0x18004a229  jz      loc_18004A394
0x18004a22f  mov     cs:?s_wndClassAtom@MessageWindow@@0GA, ax; ushort MessageWindow::s_wndClassAtom
0x18004a236  mov     [rbx+48h], r14
0x18004a23a  mov     edi, 30h ; '0'
0x18004a23f  mov     rcx, gs:60h
0x18004a248  mov     r8d, edi; Size
0x18004a24b  xor     edx, edx; Flags
0x18004a24d  mov     rcx, [rcx+30h]; HeapHandle
0x18004a251  call    cs:__imp_RtlAllocateHeap
0x18004a258  nop     dword ptr [rax+rax+00h]
0x18004a25d  test    rax, rax
0x18004a260  jz      loc_18004A7AD
0x18004a266  mov     [rax+8], rbx
0x18004a26a  lea     rcx, ??_7FocusWatcher@@6B@; const FocusWatcher::`vftable'
0x18004a271  mov     [rax], rcx
0x18004a274  mov     r8d, edi; Size
0x18004a277  mov     [rax+10h], r14d
0x18004a27b  xor     edx, edx; Flags
0x18004a27d  mov     [rax+18h], r14
0x18004a281  mov     [rax+20h], r14
0x18004a285  mov     [rax+28h], r14
0x18004a289  mov     [rbx+48h], rax
0x18004a28d  mov     [rbx+50h], r14
0x18004a291  mov     rcx, gs:60h
0x18004a29a  mov     cs:?s_singleton@FocusWatcher@@0PEAV1@EA, rax; FocusWatcher * FocusWatcher::s_singleton
0x18004a2a1  mov     rcx, [rcx+30h]; HeapHandle
0x18004a2a5  call    cs:__imp_RtlAllocateHeap
0x18004a2ac  nop     dword ptr [rax+rax+00h]
0x18004a2b1  test    rax, rax
0x18004a2b4  jz      loc_18004A75C
0x18004a2ba  mov     [rax+10h], sil
0x18004a2be  lea     rcx, ??_7RawInputWatcher@@6B@; const RawInputWatcher::`vftable'
0x18004a2c5  mov     [rax], rcx
0x18004a2c8  lea     esi, [rdi+8]
0x18004a2cb  lea     rcx, [rax+18h]
0x18004a2cf  mov     [rax+8], rbx
0x18004a2d3  mov     [rcx+10h], r14d
0x18004a2d7  mov     r8d, esi; Size
0x18004a2da  mov     [rcx+8], rcx
0x18004a2de  xor     edx, edx; Flags
0x18004a2e0  mov     [rcx], rcx
0x18004a2e3  mov     [rbx+50h], rax
0x18004a2e7  mov     [rbx+58h], r14
0x18004a2eb  mov     rcx, gs:60h
0x18004a2f4  mov     cs:?s_singleton@RawInputWatcher@@0PEAV1@EA, rax; RawInputWatcher * RawInputWatcher::s_singleton
0x18004a2fb  mov     rcx, [rcx+30h]; HeapHandle
0x18004a2ff  call    cs:__imp_RtlAllocateHeap
0x18004a306  nop     dword ptr [rax+rax+00h]
0x18004a30b  test    rax, rax
0x18004a30e  jz      loc_18004A708
0x18004a314  mov     [rax+10h], r14
0x18004a318  lea     rcx, ??_7KeyboardLayoutWatcher@@6B@; const KeyboardLayoutWatcher::`vftable'
0x18004a31f  mov     [rax], rcx
0x18004a322  mov     r8d, esi; Size
0x18004a325  mov     [rax+18h], r14
0x18004a329  xor     ecx, ecx
0x18004a32b  mov     [rax+8], rbx
0x18004a32f  xor     edx, edx; Flags
0x18004a331  mov     [rax+20h], rcx
0x18004a335  mov     [rax+28h], r14
0x18004a339  mov     [rax+30h], r14b
0x18004a33d  mov     [rbx+58h], rax
0x18004a341  mov     rcx, gs:60h
0x18004a34a  mov     cs:?s_singleton@KeyboardLayoutWatcher@@0PEAV1@EA, rax; KeyboardLayoutWatcher * KeyboardLayoutWatcher::s_singleton
0x18004a351  mov     rcx, [rcx+30h]; HeapHandle
0x18004a355  call    cs:__imp_RtlAllocateHeap
0x18004a35c  nop     dword ptr [rax+rax+00h]
0x18004a361  test    rax, rax
0x18004a364  jz      loc_18004A428
0x18004a36a  lea     rcx, ??_7PnpInterfaceWatcher@@6B@; const PnpInterfaceWatcher::`vftable'
0x18004a371  mov     [rax+8], rbx
0x18004a375  mov     [rax], rcx
0x18004a378  lea     rcx, [rax+18h]
0x18004a37c  mov     [rcx+10h], r14d
0x18004a380  mov     [rcx+8], rcx
0x18004a384  mov     [rcx], rcx
0x18004a387  mov     [rax+30h], r14
0x18004a38b  mov     [rax+10h], r14
0x18004a38f  jmp     loc_18004A42B
0x18004a394  call    cs:__imp_GetLastError
0x18004a39b  nop     dword ptr [rax+rax+00h]
0x18004a3a0  mov     edi, eax
0x18004a3a2  test    eax, eax
0x18004a3a4  jle     short loc_18004A3AF
0x18004a3a6  movzx   edi, ax
0x18004a3a9  or      edi, 80070000h
0x18004a3af  test    edi, edi
0x18004a3b1  jns     loc_18004A236
0x18004a3b7  mov     eax, cs:dword_180069000
0x18004a3bd  cmp     eax, 2
0x18004a3c0  jbe     short loc_18004A421
0x18004a3c2  mov     rcx, cs:qword_180069018
0x18004a3c9  mov     edx, 400h
0x18004a3ce  mov     rax, cs:qword_180069010
0x18004a3d5  test    rdx, rax
0x18004a3d8  jz      short loc_18004A421
0x18004a3da  mov     rax, rcx
0x18004a3dd  and     rax, rdx
0x18004a3e0  cmp     rax, rcx
0x18004a3e3  jnz     short loc_18004A421
0x18004a3e5  mov     [rbp+57h+arg_18], 109h
0x18004a3ec  lea     rdx, byte_180064333
0x18004a3f3  lea     rax, [rbp+57h+arg_10]
0x18004a3f7  mov     [rsp+0C0h+var_90], rax
0x18004a3fc  lea     rcx, aOnecoreXboxGam_2; "onecore\\xbox\\gameinput\\router\\Insta"...
0x18004a403  lea     rax, [rbp+57h+arg_18]
0x18004a407  mov     [rbp+57h+var_80], rcx
0x18004a40b  mov     [rsp+0C0h+var_98], rax
0x18004a410  lea     rax, [rbp+57h+var_80]
0x18004a414  mov     [rsp+0C0h+var_A0], rax
0x18004a419  mov     [rbp+57h+arg_10], edi
0x18004a41c  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_GameInputEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_GameInputEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x18004a421  mov     eax, edi
0x18004a423  jmp     loc_18004A827
0x18004a428  mov     rax, r14
0x18004a42b  mov     [rbx+68h], rax
0x18004a42f  mov     edi, 8007000Eh
0x18004a434  test    rax, rax
0x18004a437  jnz     short loc_18004A47A
0x18004a439  mov     eax, cs:dword_180069000
0x18004a43f  cmp     eax, 2
0x18004a442  jbe     short loc_18004A421
0x18004a444  mov     rcx, cs:qword_180069018
0x18004a44b  mov     edx, 400h
0x18004a450  mov     rax, cs:qword_180069010
0x18004a457  test    rdx, rax
0x18004a45a  jz      short loc_18004A421
0x18004a45c  mov     rax, rcx
0x18004a45f  and     rax, rdx
0x18004a462  cmp     rax, rcx
0x18004a465  jnz     short loc_18004A421
0x18004a467  mov     [rbp+57h+arg_18], 116h
0x18004a46e  lea     rdx, byte_180064669
0x18004a475  jmp     loc_18004A3F3
0x18004a47a  mov     [rbx+70h], rax
0x18004a47e  xor     edx, edx; Flags
0x18004a480  mov     rcx, gs:60h
0x18004a489  lea     r8d, [rdx+18h]; Size
0x18004a48d  mov     rcx, [rcx+30h]; HeapHandle
0x18004a491  call    cs:__imp_RtlAllocateHeap
0x18004a498  nop     dword ptr [rax+rax+00h]
0x18004a49d  test    rax, rax
0x18004a4a0  jz      short loc_18004A4B6
0x18004a4a2  lea     rcx, ??_7PnpInstanceWatcher@@6B@; const PnpInstanceWatcher::`vftable'
0x18004a4a9  mov     [rax+8], rbx
0x18004a4ad  mov     [rax], rcx
0x18004a4b0  mov     [rax+10h], r14
0x18004a4b4  jmp     short loc_18004A4B9
0x18004a4b6  mov     rax, r14
0x18004a4b9  mov     [rbx+78h], rax
0x18004a4bd  test    rax, rax
0x18004a4c0  jnz     short loc_18004A50F
0x18004a4c2  mov     eax, cs:dword_180069000
0x18004a4c8  cmp     eax, 2
0x18004a4cb  jbe     loc_18004A421
0x18004a4d1  mov     rcx, cs:qword_180069018
0x18004a4d8  mov     edx, 400h
0x18004a4dd  mov     rax, cs:qword_180069010
0x18004a4e4  test    rdx, rax
0x18004a4e7  jz      loc_18004A421
0x18004a4ed  mov     rax, rcx
0x18004a4f0  and     rax, rdx
0x18004a4f3  cmp     rax, rcx
0x18004a4f6  jnz     loc_18004A421
0x18004a4fc  mov     [rbp+57h+arg_18], 11Ah
0x18004a503  lea     rdx, byte_1800640D9
0x18004a50a  jmp     loc_18004A3F3
0x18004a50f  mov     rcx, gs:60h
0x18004a518  mov     r8, rsi; Size
0x18004a51b  xor     edx, edx; Flags
0x18004a51d  mov     rcx, [rcx+30h]; HeapHandle
0x18004a521  call    cs:__imp_RtlAllocateHeap
0x18004a528  nop     dword ptr [rax+rax+00h]
0x18004a52d  test    rax, rax
0x18004a530  jz      short loc_18004A559
0x18004a532  lea     rcx, ??_7PnpHandleWatcher@@6B@; const PnpHandleWatcher::`vftable'
0x18004a539  mov     [rax+8], rbx
0x18004a53d  mov     [rax], rcx
0x18004a540  lea     rcx, [rax+18h]
0x18004a544  mov     [rcx+10h], r14d
0x18004a548  mov     [rcx+8], rcx
0x18004a54c  mov     [rcx], rcx
0x18004a54f  mov     [rax+30h], r14
0x18004a553  mov     [rax+10h], r14
0x18004a557  jmp     short loc_18004A55C
0x18004a559  mov     rax, r14
0x18004a55c  mov     [rbx+60h], rax
0x18004a560  test    rax, rax
0x18004a563  jnz     short loc_18004A5D8
0x18004a565  mov     eax, cs:dword_180069000
0x18004a56b  cmp     eax, 2
0x18004a56e  jbe     loc_18004A421
0x18004a574  mov     rcx, cs:qword_180069018
0x18004a57b  mov     edx, 400h
0x18004a580  mov     rax, cs:qword_180069010
0x18004a587  test    rdx, rax
0x18004a58a  jz      loc_18004A421
0x18004a590  mov     rax, rcx
0x18004a593  and     rax, rdx
0x18004a596  cmp     rax, rcx
0x18004a599  jnz     loc_18004A421
0x18004a59f  lea     rcx, aOnecoreXboxGam_2; "onecore\\xbox\\gameinput\\router\\Insta"...
0x18004a5a6  mov     [rbp+57h+arg_18], 11Dh
0x18004a5ad  mov     [rbp+57h+var_80], rcx
0x18004a5b1  lea     rdx, byte_1800646B9
0x18004a5b8  lea     rcx, [rbp+57h+arg_10]
0x18004a5bc  mov     [rsp+0C0h+var_90], rcx
0x18004a5c1  lea     rcx, [rbp+57h+arg_18]
0x18004a5c5  mov     [rsp+0C0h+var_98], rcx
0x18004a5ca  lea     rcx, [rbp+57h+var_80]
0x18004a5ce  mov     [rsp+0C0h+var_A0], rcx
0x18004a5d3  jmp     loc_18004A419
0x18004a5d8  lea     rdx, [rbx+38h]; struct MessageWindow **
0x18004a5dc  mov     [rbx+80h], rax
0x18004a5e3  mov     cl, 1; bool
0x18004a5e5  call    ?CreateMessageOnlyWindow@MessageWindow@@SAJ_NPEAPEAV1@@Z; MessageWindow::CreateMessageOnlyWindow(bool,MessageWindow * *)
0x18004a5ea  mov     edi, eax
0x18004a5ec  test    eax, eax
0x18004a5ee  jns     short loc_18004A63D
0x18004a5f0  mov     ecx, cs:dword_180069000
0x18004a5f6  cmp     ecx, 2
0x18004a5f9  jbe     loc_18004A421
0x18004a5ff  mov     r8, cs:qword_180069018
0x18004a606  mov     edx, 400h
0x18004a60b  mov     rcx, cs:qword_180069010
0x18004a612  test    rdx, rcx
0x18004a615  jz      loc_18004A421
0x18004a61b  mov     rax, r8
0x18004a61e  and     rax, rdx
0x18004a621  cmp     rax, r8
0x18004a624  jnz     loc_18004A421
0x18004a62a  mov     [rbp+57h+arg_18], 122h
0x18004a631  lea     rdx, byte_180064061
0x18004a638  jmp     loc_18004A3F3
0x18004a63d  lea     rdx, [rbx+40h]; struct MessageWindow **
0x18004a641  xor     ecx, ecx; bool
0x18004a643  call    ?CreateMessageOnlyWindow@MessageWindow@@SAJ_NPEAPEAV1@@Z; MessageWindow::CreateMessageOnlyWindow(bool,MessageWindow * *)
0x18004a648  mov     edi, eax
0x18004a64a  test    eax, eax
0x18004a64c  jns     short loc_18004A69B
0x18004a64e  mov     ecx, cs:dword_180069000
0x18004a654  cmp     ecx, 2
0x18004a657  jbe     loc_18004A421
0x18004a65d  mov     r8, cs:qword_180069018
0x18004a664  mov     edx, 400h
0x18004a669  mov     rcx, cs:qword_180069010
0x18004a670  test    rdx, rcx
0x18004a673  jz      loc_18004A421
0x18004a679  mov     rax, r8
0x18004a67c  and     rax, rdx
0x18004a67f  cmp     rax, r8
0x18004a682  jnz     loc_18004A421
0x18004a688  mov     [rbp+57h+arg_18], 125h
0x18004a68f  lea     rdx, byte_180063FE7
0x18004a696  jmp     loc_18004A3F3
0x18004a69b  mov     rdx, cs:WNF_SHEL_GAMECONTROLLER_FOCUS_INFO
0x18004a6a2  lea     r8, ?OnFocusOverrideWnfChanged@Instance@@CAJU_WNF_STATE_NAME@@KPEAU_WNF_TYPE_ID@@PEAXPEBXK@Z; Instance::OnFocusOverrideWnfChanged(_WNF_STATE_NAME,ulong,_WNF_TYPE_ID *,void *,void const *,ulong)
0x18004a6a9  mov     r9, rbx
0x18004a6ac  mov     [rbp+57h+arg_0], r14d
0x18004a6b0  lea     rcx, [rbp+57h+arg_0]
0x18004a6b4  mov     [rsp+0C0h+var_A0], r14
0x18004a6b9  call    cs:__imp_RtlQueryWnfStateData
0x18004a6c0  nop     dword ptr [rax+rax+00h]
0x18004a6c5  mov     r8d, [rbp+57h+arg_0]
0x18004a6c9  lea     rcx, [rbx+90h]
0x18004a6d0  mov     rdx, cs:WNF_SHEL_GAMECONTROLLER_FOCUS_INFO
0x18004a6d7  lea     r9, ?OnFocusOverrideWnfChanged@Instance@@CAJU_WNF_STATE_NAME@@KPEAU_WNF_TYPE_ID@@PEAXPEBXK@Z; Instance::OnFocusOverrideWnfChanged(_WNF_STATE_NAME,ulong,_WNF_TYPE_ID *,void *,void const *,ulong)
0x18004a6de  mov     [rsp+0C0h+var_88], 1
0x18004a6e6  mov     dword ptr [rsp+0C0h+var_90], r14d
  ... truncated ...
```
