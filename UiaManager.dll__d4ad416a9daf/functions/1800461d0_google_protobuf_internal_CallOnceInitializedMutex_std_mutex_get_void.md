# google::protobuf::internal::CallOnceInitializedMutex<std::mutex>::get(void)

- ea: `0x1800461d0`
- end: `0x180046252`
- name: `?get@?$CallOnceInitializedMutex@Vmutex@std@@@internal@protobuf@google@@AEAAAEAVmutex@std@@XZ`
- size: `130`
- prototype: `__int64 __fastcall(LPINIT_ONCE lpInitOnce)`
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1800465e0`
- `0x1800469d0`

## callees

- `0x1800461d0`
- `0x180049ad8`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x180046233`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x180046233`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x1800461e3`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x1800461e3`

## pseudocode

```c
union _RTL_RUN_ONCE *__fastcall google::protobuf::internal::CallOnceInitializedMutex<std::mutex>::get(
        LPINIT_ONCE lpInitOnce)
{
  WINBOOL fPending; // [rsp+30h] [rbp+8h] BYREF

  if ( !__std_init_once_begin_initialize(lpInitOnce, 0, &fPending, 0) )
    __fastfail(5u);
  if ( fPending )
  {
    lpInitOnce[1].Ptr = (PVOID)2;
    *(_OWORD *)&lpInitOnce[4].Ptr = 0;
    *(_OWORD *)&lpInitOnce[6].Ptr = 0;
    *(_OWORD *)&lpInitOnce[8].Ptr = 0;
    lpInitOnce[2].Ptr = 0;
    lpInitOnce[3].Ptr = 0;
    LODWORD(lpInitOnce[10].Ptr) = -1;
    HIDWORD(lpInitOnce[10].Ptr) = 0;
    if ( !InitOnceComplete(lpInitOnce, 0, 0) )
      _std_init_once_link_alternate_names_and_abort();
  }
  return lpInitOnce + 1;
}

```

## disassembly

```asm
0x1800461d0  push    rdi
0x1800461d2  sub     rsp, 20h
0x1800461d6  xor     r9d, r9d; lpContext
0x1800461d9  lea     r8, [rsp+28h+fPending]; fPending
0x1800461de  xor     edx, edx; dwFlags
0x1800461e0  mov     rdi, rcx
0x1800461e3  call    cs:__imp___std_init_once_begin_initialize
0x1800461e9  test    eax, eax
0x1800461eb  jnz     short loc_1800461F4
0x1800461ed  mov     ecx, 5
0x1800461f2  int     29h; Win8: RtlFailFast(ecx)
0x1800461f4  cmp     [rsp+28h+fPending], 0
0x1800461f9  mov     [rsp+28h+arg_8], rbx
0x1800461fe  jz      short loc_18004623D
0x180046200  xorps   xmm0, xmm0
0x180046203  mov     qword ptr [rdi+8], 2
0x18004620b  movups  xmmword ptr [rdi+20h], xmm0
0x18004620f  xor     eax, eax
0x180046211  xor     r8d, r8d; lpContext
0x180046214  movups  xmmword ptr [rdi+30h], xmm0
0x180046218  xor     edx, edx; dwFlags
0x18004621a  mov     rcx, rdi; lpInitOnce
0x18004621d  movups  xmmword ptr [rdi+40h], xmm0
0x180046221  mov     [rdi+10h], rax
0x180046225  mov     [rdi+18h], rax
0x180046229  mov     dword ptr [rdi+50h], 0FFFFFFFFh
0x180046230  mov     [rdi+54h], eax
0x180046233  call    cs:__imp_InitOnceComplete
0x180046239  test    eax, eax
0x18004623b  jz      short loc_18004624C
0x18004623d  mov     rbx, [rsp+28h+arg_8]
0x180046242  lea     rax, [rdi+8]
0x180046246  add     rsp, 20h
0x18004624a  pop     rdi
0x18004624b  retn
0x18004624c  call    __std_init_once_link_alternate_names_and_abort
```
