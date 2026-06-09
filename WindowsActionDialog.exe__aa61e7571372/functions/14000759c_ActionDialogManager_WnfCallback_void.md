# ActionDialogManager::WnfCallback(void)

- ea: `0x14000759c`
- end: `0x14000766f`
- name: `?WnfCallback@ActionDialogManager@@QEAAJXZ`
- size: `211`
- prototype: `__int64 __fastcall(ActionDialogManager *__hidden this)`
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x140003a30`
- `0x140007a78`

## callees

- `0x140001484`
- `0x1400063c4`
- `0x14000759c`

## import_xrefs

- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x14000761f`
- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x14000761f`
- `KERNEL32!EnterCriticalSection` at `0x1400075f9`
- `KERNEL32!EnterCriticalSection` at `0x1400075f9`
- `KERNEL32!LeaveCriticalSection` at `0x14000765e`
- `KERNEL32!LeaveCriticalSection` at `0x14000765e`
- `KERNEL32!CreateEventW` at `0x1400075b4`
- `KERNEL32!CreateEventW` at `0x1400075b4`

## string_xrefs

- `0x1400075c7`: `createdHandle`

## pseudocode

```c
__int64 __fastcall ActionDialogManager::WnfCallback(ActionDialogManager *this)
{
  HANDLE EventW; // rbp
  struct _RTL_CRITICAL_SECTION *v4; // rsi
  __int64 *v5; // rdi
  __int64 v6; // rbx
  _QWORD *v7; // rax
  _QWORD *v8; // rdx
  const char *v9; // [rsp+28h] [rbp-50h]
  wil::details::in1diag5 *retaddr; // [rsp+78h] [rbp+0h]

  EventW = CreateEventW(0, 1, 0, 0);
  if ( !EventW )
    return wil::details::in1diag5::Return_GetLastError(
             retaddr,
             (void *)0xAB,
             (unsigned int)"drivers\\mobilepc\\location\\product\\winactiondialog\\exe\\actiondialog.cpp",
             "ActionDialogManager::WnfCallback",
             "createdHandle",
             v9);
  v4 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 24);
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 24));
  v5 = (__int64 *)((char *)this + 8);
  if ( v5[1] == 0xAAAAAAAAAAAAAAALL )
    std::_Xlength_error("list too long");
  v6 = *v5;
  v7 = operator new(0x18u);
  v7[2] = EventW;
  ++v5[1];
  v8 = *(_QWORD **)(v6 + 8);
  *v7 = v6;
  v7[1] = v8;
  *(_QWORD *)(v6 + 8) = v7;
  *v8 = v7;
  LeaveCriticalSection(v4);
  return 0;
}

```

## disassembly

```asm
0x14000759c  push    rbx
0x14000759e  push    rbp
0x14000759f  push    rsi
0x1400075a0  push    rdi
0x1400075a1  sub     rsp, 58h
0x1400075a5  mov     rdi, rcx
0x1400075a8  xor     r9d, r9d; lpName
0x1400075ab  xor     r8d, r8d; bInitialState
0x1400075ae  lea     edx, [r9+1]; bManualReset
0x1400075b2  xor     ecx, ecx; lpEventAttributes
0x1400075b4  call    cs:__imp_CreateEventW
0x1400075ba  mov     rbp, rax
0x1400075bd  test    rax, rax
0x1400075c0  jnz     short loc_1400075ED
0x1400075c2  mov     rcx, [rsp+78h]; this
0x1400075c7  lea     rax, aCreatedhandle; "createdHandle"
0x1400075ce  mov     [rsp+78h+var_58], rax; char *
0x1400075d3  lea     r9, aActiondialogma; "ActionDialogManager::WnfCallback"
0x1400075da  lea     r8, aDriversMobilep; "drivers\\mobilepc\\location\\product\\w"...
0x1400075e1  mov     edx, 0ABh; void *
0x1400075e6  call    ?Return_GetLastError@in1diag5@details@wil@@YAJPEAXIPEBD11@Z; wil::details::in1diag5::Return_GetLastError(void *,uint,char const *,char const *,char const *)
0x1400075eb  jmp     short loc_140007666
0x1400075ed  lea     rsi, [rdi+18h]
0x1400075f1  mov     [rsp+78h+var_48], rsi
0x1400075f6  mov     rcx, rsi; lpCriticalSection
0x1400075f9  call    cs:__imp_EnterCriticalSection
0x1400075ff  mov     [rsp+78h+var_40], 1
0x140007604  add     rdi, 8
0x140007608  mov     rax, 0AAAAAAAAAAAAAAAh
0x140007612  cmp     [rdi+8], rax
0x140007616  jnz     short loc_140007626
0x140007618  lea     rcx, aListTooLong; "list too long"
0x14000761f  call    cs:__imp_?_Xlength_error@std@@YAXPEBD@Z; std::_Xlength_error(char const *)
0x140007626  mov     rbx, [rdi]
0x140007629  mov     [rsp+78h+var_38], rdi
0x14000762e  mov     [rsp+78h+var_30], 0
0x140007637  mov     ecx, 18h; Size
0x14000763c  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x140007641  mov     [rax+10h], rbp
0x140007645  inc     qword ptr [rdi+8]
0x140007649  mov     rdx, [rbx+8]
0x14000764d  mov     [rax], rbx
0x140007650  mov     [rax+8], rdx
0x140007654  mov     [rbx+8], rax
0x140007658  mov     [rdx], rax
0x14000765b  mov     rcx, rsi; lpCriticalSection
0x14000765e  call    cs:__imp_LeaveCriticalSection
0x140007664  xor     eax, eax
0x140007666  add     rsp, 58h
0x14000766a  pop     rdi
0x14000766b  pop     rsi
0x14000766c  pop     rbp
0x14000766d  pop     rbx
0x14000766e  retn
```
