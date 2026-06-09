# Wns::CleanupTimerQueue(void *)

- ea: `0x18002ff8c`
- end: `0x18002ffc9`
- name: `?CleanupTimerQueue@Wns@@YAXPEAX@Z`
- size: `61`
- prototype: `void __fastcall(Wns *__hidden this, void *)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x18002d338`

## callees

- `0x180023300`
- `0x18002ff8c`

## import_xrefs

- `api-ms-win-core-threadpool-legacy-l1-1-0!DeleteTimerQueueEx` at `0x18002ff99`
- `api-ms-win-core-threadpool-legacy-l1-1-0!DeleteTimerQueueEx` at `0x18002ff99`

## pseudocode

```c
void __fastcall Wns::CleanupTimerQueue(Wns *this, void *a2)
{
  unsigned int v2; // eax
  const char *v3; // [rsp+28h] [rbp-10h]
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]

  if ( this != (Wns *)-1LL )
  {
    v2 = DeleteTimerQueueEx(this, (HANDLE)0xFFFFFFFFFFFFFFFFLL);
    wil::details::in1diag3::Log_IfWin32BoolFalseMsg(
      retaddr,
      (void *)0x29E,
      (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\prov\\mux\\cptransactionrequestmanager.cpp",
      (const char *)v2,
      (int)"Failed to clean up timer queue",
      v3);
  }
}

```

## disassembly

```asm
0x18002ff8c  sub     rsp, 38h
0x18002ff90  or      rdx, 0FFFFFFFFFFFFFFFFh; CompletionEvent
0x18002ff94  cmp     rcx, rdx
0x18002ff97  jz      short loc_18002FFC4
0x18002ff99  call    cs:__imp_DeleteTimerQueueEx
0x18002ff9f  mov     rcx, [rsp+38h]; this
0x18002ffa4  lea     rdx, aFailedToCleanU; "Failed to clean up timer queue"
0x18002ffab  mov     qword ptr [rsp+38h+var_18], rdx; int
0x18002ffb0  lea     r8, aOnecoreuapBase_2; "onecoreuap\\base\\diagnosis\\platform\\"...
0x18002ffb7  mov     edx, 29Eh; void *
0x18002ffbc  mov     r9d, eax; char *
0x18002ffbf  call    ?Log_IfWin32BoolFalseMsg@in1diag3@details@wil@@YAHPEAXIPEBDH1ZZ; wil::details::in1diag3::Log_IfWin32BoolFalseMsg(void *,uint,char const *,int,char const *,...)
0x18002ffc4  add     rsp, 38h
0x18002ffc8  retn
```
