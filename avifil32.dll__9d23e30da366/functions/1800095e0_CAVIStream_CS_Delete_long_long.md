# CAVIStream::CS::Delete(long,long)

- ea: `0x1800095e0`
- end: `0x180009648`
- name: `?Delete@CS@CAVIStream@@UEAAJJJ@Z`
- size: `104`
- prototype: `__int64 __fastcall(CAVIStream::CS *__hidden this, int, int)`
- caller_count: `0`
- callee_count: `1`
- tags: `file_ops`

## callees

- `0x1800095e0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800095ff`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800095ff`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000961d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180009632`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000961d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180009632`

## pseudocode

```c
__int64 __fastcall CAVIStream::CS::Delete(CAVIStream::CS *this)
{
  __int64 v1; // rbx
  struct _RTL_CRITICAL_SECTION *v2; // rdi

  v1 = *((_QWORD *)this + 1);
  v2 = (struct _RTL_CRITICAL_SECTION *)(*(_QWORD *)(v1 + 272) + 1264LL);
  EnterCriticalSection(v2);
  if ( (*(_BYTE *)(*(_QWORD *)(v1 + 272) + 660LL) & 3) != 0 )
  {
    if ( v2 )
      LeaveCriticalSection(v2);
    return 2147762277LL;
  }
  else
  {
    if ( v2 )
      LeaveCriticalSection(v2);
    return 2147762290LL;
  }
}

```

## disassembly

```asm
0x1800095e0  mov     [rsp+arg_0], rbx
0x1800095e5  push    rdi
0x1800095e6  sub     rsp, 20h
0x1800095ea  mov     rbx, [rcx+8]
0x1800095ee  mov     rdi, [rbx+110h]
0x1800095f5  add     rdi, 4F0h
0x1800095fc  mov     rcx, rdi; lpCriticalSection
0x1800095ff  call    cs:__imp_EnterCriticalSection
0x180009605  mov     rax, [rbx+110h]
0x18000960c  test    byte ptr [rax+294h], 3
0x180009613  jnz     short loc_18000962A
0x180009615  test    rdi, rdi
0x180009618  jz      short loc_180009623
0x18000961a  mov     rcx, rdi; lpCriticalSection
0x18000961d  call    cs:__imp_LeaveCriticalSection
0x180009623  mov     eax, 80044072h
0x180009628  jmp     short loc_18000963D
0x18000962a  test    rdi, rdi
0x18000962d  jz      short loc_180009638
0x18000962f  mov     rcx, rdi; lpCriticalSection
0x180009632  call    cs:__imp_LeaveCriticalSection
0x180009638  mov     eax, 80044065h
0x18000963d  mov     rbx, [rsp+28h+arg_0]
0x180009642  add     rsp, 20h
0x180009646  pop     rdi
0x180009647  retn
```
