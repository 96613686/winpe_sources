# MessageWindow::CreateMessageOnlyWindow(bool,MessageWindow * *)

- ea: `0x1800495e4`
- end: `0x1800496f4`
- name: `?CreateMessageOnlyWindow@MessageWindow@@SAJ_NPEAPEAV1@@Z`
- size: `272`
- prototype: `__int64 __fastcall(bool, struct MessageWindow **)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, loader_planting`

## callers

- `0x18004a1a4`

## callees

- `0x180001304`
- `0x18000c11c`
- `0x180049198`
- `0x180049520`
- `0x1800495e4`

## import_xrefs

- `ntdll!RtlAllocateHeap` at `0x18004960c`
- `ntdll!RtlAllocateHeap` at `0x18004960c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180049645`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180049645`

## pseudocode

```c
__int64 __fastcall MessageWindow::CreateMessageOnlyWindow(char a1, HANDLE **a2)
{
  HANDLE *Heap; // rax
  __int64 v5; // r8
  __int64 v6; // r9
  HANDLE *v7; // rbx
  signed int LastError; // eax
  unsigned int v10; // edi
  const struct std::nothrow_t *v11; // rdx
  int v12; // [rsp+68h] [rbp+10h] BYREF
  int v13; // [rsp+70h] [rbp+18h] BYREF
  const char *v14; // [rsp+78h] [rbp+20h] BYREF

  *a2 = 0;
  Heap = (HANDLE *)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, 0x10u);
  v7 = Heap;
  if ( Heap )
  {
    *Heap = 0;
    *((_BYTE *)Heap + 9) = 0;
    *((_BYTE *)Heap + 8) = a1;
    if ( (int)MessageWindow::CreateMessageOnlyThread((MessageWindow *)Heap) < 0 )
    {
      LastError = GetLastError();
      v10 = LastError;
      if ( LastError > 0 )
        v10 = (unsigned __int16)LastError | 0x80070000;
      MessageWindow::~MessageWindow(v7);
      operator delete(v7, v11);
      return v10;
    }
    else
    {
      *a2 = v7;
      return 0;
    }
  }
  else
  {
    if ( (unsigned int)dword_180069000 > 2
      && (qword_180069010 & 0x400) != 0
      && (qword_180069018 & 0x400) == qword_180069018 )
    {
      v12 = -2147024882;
      v14 = "onecore\\xbox\\gameinput\\router\\MessageWindow.cpp";
      v13 = 91;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_GameInputEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        (__int64)&v14,
        (unsigned __int8 *)byte_180064269,
        v5,
        v6,
        (__int64 **)&v14,
        (__int64)&v13,
        (__int64)&v12);
    }
    return 2147942414LL;
  }
}

```

## disassembly

```asm
0x1800495e4  push    rbx
0x1800495e6  push    rsi
0x1800495e7  push    rdi
0x1800495e8  sub     rsp, 40h
0x1800495ec  mov     qword ptr [rdx], 0
0x1800495f3  mov     sil, cl
0x1800495f6  mov     rcx, gs:60h
0x1800495ff  mov     rdi, rdx
0x180049602  xor     edx, edx; Flags
0x180049604  mov     rcx, [rcx+30h]; HeapHandle
0x180049608  lea     r8d, [rdx+10h]; Size
0x18004960c  call    cs:__imp_RtlAllocateHeap
0x180049613  nop     dword ptr [rax+rax+00h]
0x180049618  mov     rbx, rax
0x18004961b  test    rax, rax
0x18004961e  jz      short loc_180049674
0x180049620  mov     qword ptr [rax], 0
0x180049627  mov     rcx, rax; this
0x18004962a  mov     byte ptr [rax+9], 0
0x18004962e  mov     [rax+8], sil
0x180049632  call    ?CreateMessageOnlyThread@MessageWindow@@AEAAJXZ; MessageWindow::CreateMessageOnlyThread(void)
0x180049637  test    eax, eax
0x180049639  js      short loc_180049645
0x18004963b  mov     [rdi], rbx
0x18004963e  xor     eax, eax
0x180049640  jmp     loc_1800496EB
0x180049645  call    cs:__imp_GetLastError
0x18004964c  nop     dword ptr [rax+rax+00h]
0x180049651  mov     edi, eax
0x180049653  test    eax, eax
0x180049655  jle     short loc_180049660
0x180049657  movzx   edi, ax
0x18004965a  or      edi, 80070000h
0x180049660  mov     rcx, rbx; this
0x180049663  call    ??1MessageWindow@@QEAA@XZ; MessageWindow::~MessageWindow(void)
0x180049668  mov     rcx, rbx; P
0x18004966b  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180049670  mov     eax, edi
0x180049672  jmp     short loc_1800496EB
0x180049674  mov     eax, cs:dword_180069000
0x18004967a  mov     ebx, 8007000Eh
0x18004967f  cmp     eax, 2
0x180049682  jbe     short loc_1800496E9
0x180049684  mov     rcx, cs:qword_180069018
0x18004968b  mov     edx, 400h
0x180049690  mov     rax, cs:qword_180069010
0x180049697  test    rdx, rax
0x18004969a  jz      short loc_1800496E9
0x18004969c  mov     rax, rcx
0x18004969f  and     rax, rdx
0x1800496a2  cmp     rax, rcx
0x1800496a5  jnz     short loc_1800496E9
0x1800496a7  lea     rcx, aOnecoreXboxGam_40; "onecore\\xbox\\gameinput\\router\\Messa"...
0x1800496ae  mov     [rsp+58h+arg_8], ebx
0x1800496b2  mov     [rsp+58h+arg_18], rcx
0x1800496b7  lea     rdx, byte_180064269
0x1800496be  lea     rcx, [rsp+58h+arg_8]
0x1800496c3  mov     [rsp+58h+arg_10], 5Bh ; '['
0x1800496cb  mov     [rsp+58h+var_28], rcx
0x1800496d0  lea     rcx, [rsp+58h+arg_10]
0x1800496d5  mov     [rsp+58h+var_30], rcx
0x1800496da  lea     rcx, [rsp+58h+arg_18]
0x1800496df  mov     [rsp+58h+var_38], rcx
0x1800496e4  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_GameInputEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_GameInputEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x1800496e9  mov     eax, ebx
0x1800496eb  add     rsp, 40h
0x1800496ef  pop     rdi
0x1800496f0  pop     rsi
0x1800496f1  pop     rbx
0x1800496f2  retn
```
