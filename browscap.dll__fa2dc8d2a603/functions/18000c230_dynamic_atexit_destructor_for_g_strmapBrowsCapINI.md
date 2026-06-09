# _dynamic_atexit_destructor_for__g_strmapBrowsCapINI__

- ea: `0x18000c230`
- end: `0x18000c283`
- name: `_dynamic_atexit_destructor_for__g_strmapBrowsCapINI__`
- size: `83`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x180002498`
- `0x18000c230`

## import_xrefs

- `msvcrt!free` at `0x18000c277`
- `msvcrt!free` at `0x18000c277`
- `KERNEL32!DeleteCriticalSection` at `0x18000c23d`
- `KERNEL32!DeleteCriticalSection` at `0x18000c23d`

## pseudocode

```c
void dynamic_atexit_destructor_for__g_strmapBrowsCapINI__()
{
  char *v0; // rbx

  DeleteCriticalSection(&stru_180012948);
  v0 = (char *)qword_180012938;
  if ( qword_180012938 != Src )
  {
    do
    {
      TRefPtr<CMonitorNotify>::~TRefPtr<CMonitorNotify>(v0);
      v0 += 24;
    }
    while ( v0 != Src );
    v0 = (char *)qword_180012938;
  }
  if ( v0 )
    free(v0);
}

```

## disassembly

```asm
0x18000c230  push    rbx
0x18000c232  sub     rsp, 20h
0x18000c236  lea     rcx, stru_180012948; lpCriticalSection
0x18000c23d  call    cs:__imp_DeleteCriticalSection
0x18000c243  mov     rbx, cs:qword_180012938
0x18000c24a  cmp     rbx, cs:Src
0x18000c251  jz      short loc_18000C26F
0x18000c253  mov     rcx, rbx
0x18000c256  call    ??1?$TRefPtr@VCMonitorNotify@@@@QEAA@XZ; TRefPtr<CMonitorNotify>::~TRefPtr<CMonitorNotify>(void)
0x18000c25b  add     rbx, 18h
0x18000c25f  cmp     rbx, cs:Src
0x18000c266  jnz     short loc_18000C253
0x18000c268  mov     rbx, cs:qword_180012938
0x18000c26f  test    rbx, rbx
0x18000c272  jz      short loc_18000C27D
0x18000c274  mov     rcx, rbx; Block
0x18000c277  call    cs:__imp_free
0x18000c27d  add     rsp, 20h
0x18000c281  pop     rbx
0x18000c282  retn
```
