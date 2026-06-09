# InterfaceLifetimeTracking::InterfaceLifetimeTracking(ulong)

- ea: `0x18006c218`
- end: `0x18006c2ba`
- name: `??0InterfaceLifetimeTracking@@QEAA@K@Z`
- size: `162`
- prototype: `InterfaceLifetimeTracking *__fastcall(PVOID pv, unsigned int)`
- caller_count: `2`
- callee_count: `2`
- tags: `service_task`

## callers

- `0x1800cb1d4`
- `0x1800ccfc4`

## callees

- `0x18006c218`
- `0x18006c2c0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18006c238`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18006c238`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x18006c2a5`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x18006c2a5`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWait` at `0x18006c24e`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWait` at `0x18006c24e`

## string_xrefs

- `0x18006c270`: `onecoreuap\net\wcm\service\base\selection\lib\InterfaceLifetimeTracking.h`
- `0x18006c28c`: `onecoreuap\net\wcm\service\base\selection\lib\InterfaceLifetimeTracking.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
HANDLE *__fastcall InterfaceLifetimeTracking::InterfaceLifetimeTracking(HANDLE *pv, int a2)
{
  struct _TP_WAIT *ThreadpoolWait; // rax
  const char *v5; // r9
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  *pv = CreateEventW(0, 1, 0, 0);
  ThreadpoolWait = CreateThreadpoolWait(InterfaceLifetimeTracking::InterfaceLifetimeTrackingCallback, pv, 0);
  pv[1] = ThreadpoolWait;
  *((_DWORD *)pv + 4) = a2;
  v5 = (const char *)*pv;
  if ( (((unsigned __int64)*pv + 1) & 0xFFFFFFFFFFFFFFFEuLL) == 0 )
    wil::details::in1diag3::_Throw_NullAlloc(
      retaddr,
      (void *)0x12,
      (unsigned int)"onecoreuap\\net\\wcm\\service\\base\\selection\\lib\\InterfaceLifetimeTracking.h",
      v5);
  if ( !ThreadpoolWait )
    wil::details::in1diag3::_Throw_NullAlloc(
      retaddr,
      (void *)0x13,
      (unsigned int)"onecoreuap\\net\\wcm\\service\\base\\selection\\lib\\InterfaceLifetimeTracking.h",
      v5);
  SetThreadpoolWait(ThreadpoolWait, *pv, 0);
  return pv;
}

```

## disassembly

```asm
0x18006c218  mov     [rsp+arg_8], rbx
0x18006c21d  mov     [rsp+arg_0], rcx
0x18006c222  push    rdi
0x18006c223  sub     rsp, 20h
0x18006c227  mov     ebx, edx
0x18006c229  mov     rdi, rcx
0x18006c22c  xor     r9d, r9d; lpName
0x18006c22f  xor     r8d, r8d; bInitialState
0x18006c232  lea     edx, [r9+1]; bManualReset
0x18006c236  xor     ecx, ecx; lpEventAttributes
0x18006c238  call    cs:__imp_CreateEventW
0x18006c23e  mov     [rdi], rax
0x18006c241  xor     r8d, r8d; pcbe
0x18006c244  mov     rdx, rdi; pv
0x18006c247  lea     rcx, ?InterfaceLifetimeTrackingCallback@InterfaceLifetimeTracking@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WAIT@@J@Z; pfnwa
0x18006c24e  call    cs:__imp_CreateThreadpoolWait
0x18006c254  mov     [rdi+8], rax
0x18006c258  mov     [rdi+10h], ebx
0x18006c25b  mov     rcx, [rsp+28h]; this
0x18006c260  mov     r9, [rdi]; char *
0x18006c263  lea     rdx, [r9+1]
0x18006c267  test    rdx, 0FFFFFFFFFFFFFFFEh
0x18006c26e  jnz     short loc_18006C282
0x18006c270  lea     r8, aOnecoreuapNetW_12; "onecoreuap\\net\\wcm\\service\\base\\se"...
0x18006c277  mov     edx, 12h; void *
0x18006c27c  call    ?_Throw_NullAlloc@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_NullAlloc(void *,uint,char const *)
0x18006c282  mov     rcx, [rsp+28h]; this
0x18006c287  test    rax, rax
0x18006c28a  jnz     short loc_18006C29C
0x18006c28c  lea     r8, aOnecoreuapNetW_12; "onecoreuap\\net\\wcm\\service\\base\\se"...
0x18006c293  lea     edx, [rax+13h]; void *
0x18006c296  call    ?_Throw_NullAlloc@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_NullAlloc(void *,uint,char const *)
0x18006c29c  xor     r8d, r8d; pftTimeout
0x18006c29f  mov     rdx, r9; h
0x18006c2a2  mov     rcx, rax; pwa
0x18006c2a5  call    cs:__imp_SetThreadpoolWait
0x18006c2ab  nop
0x18006c2ac  mov     rax, rdi
0x18006c2af  mov     rbx, [rsp+28h+arg_8]
0x18006c2b4  add     rsp, 20h
0x18006c2b8  pop     rdi
0x18006c2b9  retn
```
