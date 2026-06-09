# RawInputWatcher::GetRawInputDeviceName(void * const,utl::unique_ptr<ushort [0],utl::default_delete<ushort [0]>> *)

- ea: `0x18004a07c`
- end: `0x18004a19e`
- name: `?GetRawInputDeviceName@RawInputWatcher@@AEAAXQEAXPEAV?$unique_ptr@$$BY0A@GU?$default_delete@$$BY0A@G@utl@@@utl@@@Z`
- size: `290`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops, loader_planting`

## callers

- `0x180049fa4`

## callees

- `0x180001540`
- `0x18000c11c`
- `0x18004a07c`

## import_xrefs

- `ntdll!RtlAllocateHeap` at `0x18004a0bf`
- `ntdll!RtlAllocateHeap` at `0x18004a0bf`
- `ext-ms-win-ntuser-rawinput-l1-1-0!GetRawInputDeviceInfoW` at `0x18004a0e7`
- `ext-ms-win-ntuser-rawinput-l1-1-0!GetRawInputDeviceInfoW` at `0x18004a0e7`

## pseudocode

```c
void __fastcall RawInputWatcher::GetRawInputDeviceName(__int64 a1, const struct std::nothrow_t *a2, void **a3)
{
  void *v3; // rcx
  PVOID Heap; // rax
  PVOID v7; // rdi
  __int64 v8; // rdx
  __int64 v9; // r8
  __int64 v10; // r9
  void *v11; // rcx
  const char *v12; // [rsp+40h] [rbp-28h] BYREF
  __int64 pcbSize; // [rsp+70h] [rbp+8h] BYREF
  int v14; // [rsp+80h] [rbp+18h] BYREF
  const char *v15; // [rsp+88h] [rbp+20h] BYREF

  pcbSize = a1;
  v3 = *a3;
  *a3 = 0;
  if ( v3 )
    operator delete(v3, a2);
  LODWORD(pcbSize) = 200;
  Heap = RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, 0x192u);
  v7 = Heap;
  if ( Heap )
  {
    if ( GetRawInputDeviceInfoW(a2, 0x20000007u, Heap, (PUINT)&pcbSize) == -1 )
    {
      if ( (unsigned int)dword_180069000 > 2 )
      {
        v8 = 1024;
        if ( (qword_180069010 & 0x400) != 0 && (qword_180069018 & 0x400) == qword_180069018 )
        {
          v14 = 56;
          v15 = "GetRawInputDeviceInfo failed.";
          v12 = "onecore\\xbox\\gameinput\\router\\RawInputWatcher.cpp";
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_GameInputEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
            qword_180069018,
            (unsigned __int8 *)byte_180064441,
            v9,
            v10,
            (__int64 **)&v12,
            (__int64)&v14,
            (__int64 **)&v15);
        }
      }
      v11 = v7;
    }
    else
    {
      v11 = *a3;
      *a3 = v7;
      if ( !v11 )
        return;
    }
    operator delete(v11, (const struct std::nothrow_t *)v8);
  }
}

```

## disassembly

```asm
0x18004a07c  mov     [rsp+pcbSize], rcx
0x18004a081  push    rbx
0x18004a082  push    rsi
0x18004a083  push    rdi
0x18004a084  sub     rsp, 50h
0x18004a088  mov     rcx, [r8]; P
0x18004a08b  mov     rbx, r8
0x18004a08e  mov     qword ptr [r8], 0
0x18004a095  mov     rsi, rdx
0x18004a098  test    rcx, rcx
0x18004a09b  jz      short loc_18004A0A2
0x18004a09d  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18004a0a2  mov     dword ptr [rsp+68h+pcbSize], 0C8h
0x18004a0aa  xor     edx, edx; Flags
0x18004a0ac  mov     rcx, gs:60h
0x18004a0b5  mov     r8d, 192h; Size
0x18004a0bb  mov     rcx, [rcx+30h]; HeapHandle
0x18004a0bf  call    cs:__imp_RtlAllocateHeap
0x18004a0c6  nop     dword ptr [rax+rax+00h]
0x18004a0cb  mov     rdi, rax
0x18004a0ce  test    rax, rax
0x18004a0d1  jz      loc_18004A195
0x18004a0d7  lea     r9, [rsp+68h+pcbSize]; pcbSize
0x18004a0dc  mov     r8, rax; pData
0x18004a0df  mov     edx, 20000007h; uiCommand
0x18004a0e4  mov     rcx, rsi; hDevice
0x18004a0e7  call    cs:__imp_GetRawInputDeviceInfoW
0x18004a0ee  nop     dword ptr [rax+rax+00h]
0x18004a0f3  cmp     eax, 0FFFFFFFFh
0x18004a0f6  jnz     loc_18004A185
0x18004a0fc  mov     ecx, cs:dword_180069000
0x18004a102  cmp     ecx, 2
0x18004a105  jbe     short loc_18004A180
0x18004a107  mov     rcx, cs:qword_180069018
0x18004a10e  mov     edx, 400h
0x18004a113  mov     rax, cs:qword_180069010
0x18004a11a  test    rdx, rax
0x18004a11d  jz      short loc_18004A180
0x18004a11f  mov     rax, rcx
0x18004a122  and     rax, rdx
0x18004a125  cmp     rax, rcx
0x18004a128  jnz     short loc_18004A180
0x18004a12a  lea     rax, aGetrawinputdev_0; "GetRawInputDeviceInfo failed."
0x18004a131  mov     [rsp+68h+arg_10], 38h ; '8'
0x18004a13c  mov     [rsp+68h+arg_18], rax
0x18004a144  lea     rdx, byte_180064441
0x18004a14b  lea     rax, aOnecoreXboxGam_51; "onecore\\xbox\\gameinput\\router\\RawIn"...
0x18004a152  mov     [rsp+68h+var_28], rax
0x18004a157  lea     rax, [rsp+68h+arg_18]
0x18004a15f  mov     [rsp+68h+var_38], rax
0x18004a164  lea     rax, [rsp+68h+arg_10]
0x18004a16c  mov     [rsp+68h+var_40], rax
0x18004a171  lea     rax, [rsp+68h+var_28]
0x18004a176  mov     [rsp+68h+var_48], rax
0x18004a17b  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_GameInputEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@3@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_GameInputEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x18004a180  mov     rcx, rdi
0x18004a183  jmp     short loc_18004A190
0x18004a185  mov     rcx, [rbx]; P
0x18004a188  mov     [rbx], rdi
0x18004a18b  test    rcx, rcx
0x18004a18e  jz      short loc_18004A195
0x18004a190  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18004a195  add     rsp, 50h
0x18004a199  pop     rdi
0x18004a19a  pop     rsi
0x18004a19b  pop     rbx
0x18004a19c  retn
```
