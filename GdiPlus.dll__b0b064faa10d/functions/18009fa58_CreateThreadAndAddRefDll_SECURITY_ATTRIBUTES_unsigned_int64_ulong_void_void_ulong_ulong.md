# CreateThreadAndAddRefDll(_SECURITY_ATTRIBUTES *,unsigned __int64,ulong (*)(void *),void *,ulong,ulong *)

- ea: `0x18009fa58`
- end: `0x18009fb07`
- name: `?CreateThreadAndAddRefDll@@YAPEAXPEAU_SECURITY_ATTRIBUTES@@_KP6AKPEAX@Z2KPEAK@Z`
- size: `175`
- prototype: `void *__fastcall(struct _SECURITY_ATTRIBUTES *, unsigned __int64, unsigned int (*)(void *), void *, unsigned int, unsigned int *)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18009f9ac`

## callees

- `0x18009fa58`
- `0x18009fb10`
- `0x1800e1500`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18009faf5`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18009faf5`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18009fa8e`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18009fa8e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18009fa7f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18009fa7f`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x18009fad1`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x18009fad1`

## pseudocode

```c
HANDLE __fastcall CreateThreadAndAddRefDll(
        struct _SECURITY_ATTRIBUTES *a1,
        __int64 a2,
        unsigned int (*a3)(void *),
        void *a4)
{
  HANDLE Thread; // rdi
  HANDLE ProcessHeap; // rax
  wil::details *v6; // rax
  HMODULE v7; // rsi
  wil::details *v8; // rbx
  void *v9; // rdx
  HMODULE hLibModule; // [rsp+58h] [rbp+20h] BYREF

  Thread = 0;
  hLibModule = 0;
  if ( (unsigned int)AddRefModule(&hLibModule) )
  {
    ProcessHeap = GetProcessHeap();
    v6 = (wil::details *)HeapAlloc(ProcessHeap, 0, 0x18u);
    v7 = hLibModule;
    v8 = v6;
    if ( v6 )
    {
      *((_QWORD *)v6 + 1) = 0;
      *(_QWORD *)v6 = BackgroundThreadProc;
      *((_QWORD *)v6 + 2) = v7;
      Thread = CreateThread(0, 0, DllRefCountSafeThreadThunk, v6, 0, &Globals::ThreadId);
      if ( Thread )
        return Thread;
      wil::details::FreeProcessHeap(v8, v9);
    }
    FreeLibrary(v7);
  }
  return Thread;
}

```

## disassembly

```asm
0x18009fa58  mov     rax, rsp
0x18009fa5b  mov     [rax+8], rbx
0x18009fa5f  mov     [rax+10h], rsi
0x18009fa63  mov     [rax+20h], r9
0x18009fa67  push    rdi
0x18009fa68  sub     rsp, 30h
0x18009fa6c  xor     edi, edi
0x18009fa6e  lea     rcx, [rax+20h]; HINSTANCE *
0x18009fa72  mov     [rax+20h], rdi
0x18009fa76  call    ?AddRefModule@@YAHPEAPEAUHINSTANCE__@@@Z; AddRefModule(HINSTANCE__ * *)
0x18009fa7b  test    eax, eax
0x18009fa7d  jz      short loc_18009FADF
0x18009fa7f  call    cs:__imp_GetProcessHeap
0x18009fa85  xor     edx, edx; dwFlags
0x18009fa87  lea     r8d, [rdi+18h]; dwBytes
0x18009fa8b  mov     rcx, rax; hHeap
0x18009fa8e  call    cs:__imp_HeapAlloc
0x18009fa94  mov     rsi, [rsp+38h+hLibModule]
0x18009fa99  mov     rbx, rax
0x18009fa9c  test    rax, rax
0x18009fa9f  jz      short loc_18009FAF2
0x18009faa1  lea     rax, ?BackgroundThreadProc@@YAKPEAX@Z; BackgroundThreadProc(void *)
0x18009faa8  mov     [rbx+8], rdi
0x18009faac  mov     [rbx], rax
0x18009faaf  lea     r8, ?DllRefCountSafeThreadThunk@@YAKPEAX@Z; lpStartAddress
0x18009fab6  lea     rax, ?ThreadId@Globals@@3KA; ulong Globals::ThreadId
0x18009fabd  mov     [rbx+10h], rsi
0x18009fac1  mov     [rsp+38h+lpThreadId], rax; lpThreadId
0x18009fac6  mov     r9, rbx; lpParameter
0x18009fac9  xor     edx, edx; dwStackSize
0x18009facb  mov     [rsp+38h+dwCreationFlags], edi; dwCreationFlags
0x18009facf  xor     ecx, ecx; lpThreadAttributes
0x18009fad1  call    cs:__imp_CreateThread
0x18009fad7  mov     rdi, rax
0x18009fada  test    rax, rax
0x18009fadd  jz      short loc_18009FAFD
0x18009fadf  mov     rbx, [rsp+38h+arg_0]
0x18009fae4  mov     rax, rdi
0x18009fae7  mov     rsi, [rsp+38h+arg_8]
0x18009faec  add     rsp, 30h
0x18009faf0  pop     rdi
0x18009faf1  retn
0x18009faf2  mov     rcx, rsi; hLibModule
0x18009faf5  call    cs:__imp_FreeLibrary
0x18009fafb  jmp     short loc_18009FADF
0x18009fafd  mov     rcx, rbx; this
0x18009fb00  call    ?FreeProcessHeap@details@wil@@YAXPEAX@Z; wil::details::FreeProcessHeap(void *)
0x18009fb05  jmp     short loc_18009FAF2
```
