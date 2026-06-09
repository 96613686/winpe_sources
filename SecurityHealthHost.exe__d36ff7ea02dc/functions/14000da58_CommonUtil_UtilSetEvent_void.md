# CommonUtil::UtilSetEvent(void *)

- ea: `0x14000da58`
- end: `0x14000daa1`
- name: `?UtilSetEvent@CommonUtil@@YAXPEAX@Z`
- size: `73`
- prototype: `void __fastcall(CommonUtil *__hidden this, void *)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x140004350`

## callees

- `0x140003040`
- `0x14000da58`
- `0x14000f7c8`

## import_xrefs

- `KERNEL32!SetEvent` at `0x14000da5c`
- `KERNEL32!SetEvent` at `0x14000da5c`

## pseudocode

```c
void __fastcall CommonUtil::UtilSetEvent(CommonUtil *this, void *a2)
{
  unsigned int LastFailure; // eax

  if ( !SetEvent(this) )
  {
    LastFailure = HrGetLastFailure();
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 13, WPP_b11265c829643c9fe11ce3dfb10c34a9_Traceguids, LastFailure);
  }
}

```

## disassembly

```asm
0x14000da58  sub     rsp, 28h
0x14000da5c  call    cs:__imp_SetEvent
0x14000da62  test    eax, eax
0x14000da64  jnz     short loc_14000DA9C
0x14000da66  call    HrGetLastFailure
0x14000da6b  mov     rcx, cs:WPP_GLOBAL_Control
0x14000da72  lea     rdx, WPP_GLOBAL_Control
0x14000da79  cmp     rcx, rdx
0x14000da7c  jz      short loc_14000DA9C
0x14000da7e  test    byte ptr [rcx+1Ch], 1
0x14000da82  jz      short loc_14000DA9C
0x14000da84  mov     rcx, [rcx+10h]
0x14000da88  lea     r8, WPP_b11265c829643c9fe11ce3dfb10c34a9_Traceguids
0x14000da8f  mov     edx, 0Dh
0x14000da94  mov     r9d, eax
0x14000da97  call    WPP_SF_d
0x14000da9c  add     rsp, 28h
0x14000daa0  retn
```
