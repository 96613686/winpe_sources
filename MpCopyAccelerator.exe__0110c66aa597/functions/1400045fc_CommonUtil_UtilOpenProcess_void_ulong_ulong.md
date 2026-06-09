# CommonUtil::UtilOpenProcess(void * *,ulong,ulong)

- ea: `0x1400045fc`
- end: `0x14000466e`
- name: `?UtilOpenProcess@CommonUtil@@YAJPEAPEAXKK@Z`
- size: `114`
- prototype: `int(CommonUtil *__hidden this, void **, unsigned int, unsigned int)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x14001e654`

## callees

- `0x1400045fc`
- `0x14000493c`
- `0x1400203f0`

## import_xrefs

- `KERNEL32!OpenProcess` at `0x140004615`
- `KERNEL32!OpenProcess` at `0x140004615`

## pseudocode

```c
__int64 __fastcall CommonUtil::UtilOpenProcess(CommonUtil *this, void **a2, DWORD a3)
{
  unsigned int v3; // edi
  HANDLE v5; // rax
  unsigned int LastFailure; // ebx

  v3 = (unsigned int)a2;
  v5 = OpenProcess(a3, 0, (DWORD)a2);
  *(_QWORD *)this = v5;
  LastFailure = 0;
  if ( !v5 )
    LastFailure = HrGetLastFailure();
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    WPP_SF_Dd(*((_QWORD *)WPP_GLOBAL_Control + 2), 39, WPP_bed851edf8673fd54b380593fb017a56_Traceguids, v3, LastFailure);
  return LastFailure;
}

```

## disassembly

```asm
0x1400045fc  mov     [rsp+arg_0], rbx
0x140004601  push    rdi
0x140004602  sub     rsp, 30h
0x140004606  mov     eax, r8d
0x140004609  mov     edi, edx
0x14000460b  mov     r8d, edx; dwProcessId
0x14000460e  mov     rbx, rcx
0x140004611  xor     edx, edx; bInheritHandle
0x140004613  mov     ecx, eax; dwDesiredAccess
0x140004615  call    cs:__imp_OpenProcess
0x14000461b  mov     [rbx], rax
0x14000461e  xor     ebx, ebx
0x140004620  test    rax, rax
0x140004623  jnz     short loc_14000462C
0x140004625  call    HrGetLastFailure
0x14000462a  mov     ebx, eax
0x14000462c  mov     rcx, cs:WPP_GLOBAL_Control
0x140004633  lea     rax, WPP_GLOBAL_Control
0x14000463a  cmp     rcx, rax
0x14000463d  jz      short loc_140004661
0x14000463f  test    byte ptr [rcx+1Ch], 4
0x140004643  jz      short loc_140004661
0x140004645  mov     rcx, [rcx+10h]
0x140004649  lea     r8, WPP_bed851edf8673fd54b380593fb017a56_Traceguids
0x140004650  mov     edx, 27h ; '''
0x140004655  mov     [rsp+38h+var_18], ebx
0x140004659  mov     r9d, edi
0x14000465c  call    WPP_SF_Dd
0x140004661  mov     eax, ebx
0x140004663  mov     rbx, [rsp+38h+arg_0]
0x140004668  add     rsp, 30h
0x14000466c  pop     rdi
0x14000466d  retn
```
