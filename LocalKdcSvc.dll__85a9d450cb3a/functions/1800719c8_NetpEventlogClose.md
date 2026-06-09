# NetpEventlogClose

- ea: `0x1800719c8`
- end: `0x180071a35`
- name: `NetpEventlogClose`
- size: `109`
- prototype: `__int64 __fastcall(LPCRITICAL_SECTION lpCriticalSection)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x180035a44`
- `0x18006e0c8`

## callees

- `0x1800719c8`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800719d5`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800719d5`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180071a12`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180071a12`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180071a1b`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180071a1b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180071a00`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180071a00`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180071a2e`

## pseudocode

```c
HLOCAL __fastcall NetpEventlogClose(LPCRITICAL_SECTION lpCriticalSection)
{
  LPCRITICAL_SECTION v2; // rdi
  _QWORD *p_Type; // rcx
  __int64 v4; // rax
  _QWORD *v5; // rdx

  EnterCriticalSection(lpCriticalSection);
  v2 = lpCriticalSection + 1;
  while ( 1 )
  {
    p_Type = &v2->DebugInfo->Type;
    if ( (LPCRITICAL_SECTION)v2->DebugInfo == v2 )
      break;
    v4 = *p_Type;
    if ( *(_QWORD **)(*p_Type + 8LL) != p_Type || (v5 = (_QWORD *)p_Type[1], (_QWORD *)*v5 != p_Type) )
      __fastfail(3u);
    *v5 = v4;
    *(_QWORD *)(v4 + 8) = v5;
    LocalFree(p_Type);
  }
  LeaveCriticalSection(lpCriticalSection);
  DeleteCriticalSection(lpCriticalSection);
  return LocalFree(lpCriticalSection);
}

```

## disassembly

```asm
0x1800719c8  mov     [rsp+arg_0], rbx
0x1800719cd  push    rdi
0x1800719ce  sub     rsp, 20h
0x1800719d2  mov     rbx, rcx
0x1800719d5  call    cs:__imp_EnterCriticalSection
0x1800719db  lea     rdi, [rbx+28h]
0x1800719df  mov     rcx, [rdi]; hMem
0x1800719e2  cmp     rcx, rdi
0x1800719e5  jz      short loc_180071A0F
0x1800719e7  mov     rax, [rcx]
0x1800719ea  cmp     [rax+8], rcx
0x1800719ee  jnz     short loc_180071A08
0x1800719f0  mov     rdx, [rcx+8]
0x1800719f4  cmp     [rdx], rcx
0x1800719f7  jnz     short loc_180071A08
0x1800719f9  mov     [rdx], rax
0x1800719fc  mov     [rax+8], rdx
0x180071a00  call    cs:__imp_LocalFree
0x180071a06  jmp     short loc_1800719DF
0x180071a08  mov     ecx, 3
0x180071a0d  int     29h; Win8: RtlFailFast(ecx)
0x180071a0f  mov     rcx, rbx; lpCriticalSection
0x180071a12  call    cs:__imp_LeaveCriticalSection
0x180071a18  mov     rcx, rbx; lpCriticalSection
0x180071a1b  call    cs:__imp_DeleteCriticalSection
0x180071a21  mov     rcx, rbx
0x180071a24  mov     rbx, [rsp+28h+arg_0]
0x180071a29  add     rsp, 20h
0x180071a2d  pop     rdi
0x180071a2e  jmp     cs:__imp_LocalFree
```
