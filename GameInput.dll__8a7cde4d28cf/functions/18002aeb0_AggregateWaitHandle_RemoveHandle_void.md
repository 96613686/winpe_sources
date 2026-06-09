# AggregateWaitHandle::RemoveHandle(void *)

- ea: `0x18002aeb0`
- end: `0x18002af40`
- name: `?RemoveHandle@AggregateWaitHandle@@QEAAJPEAX@Z`
- size: `144`
- prototype: `__int64 __fastcall(AggregateWaitHandle *__hidden this, void *)`
- caller_count: `4`
- callee_count: `2`
- tags: `file_ops, loader_planting, broker_com_uri`

## callers

- `0x180024e3c`
- `0x180024efc`
- `0x180028500`
- `0x18002bb00`

## callees

- `0x18000c11c`
- `0x18002aeb0`

## import_xrefs

- `ntdll!NtCancelWaitCompletionPacket` at `0x18002aeda`
- `ntdll!NtCancelWaitCompletionPacket` at `0x18002aeda`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002aeee`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002aeee`

## pseudocode

```c
int __fastcall AggregateWaitHandle::RemoveHandle(AggregateWaitHandle *this, void *a2)
{
  __int64 *i; // rbx
  int v4; // eax
  const struct std::nothrow_t *v5; // rdx
  __int64 *v6; // rcx
  __int64 **v7; // rax

  for ( i = (__int64 *)*((_QWORD *)this + 3); ; i = (__int64 *)*i )
  {
    if ( i == (__int64 *)((char *)this + 24) )
      return -805305616;
    if ( (void *)i[2] == a2 )
      break;
  }
  LOBYTE(a2) = 1;
  v4 = NtCancelWaitCompletionPacket(i[3], a2);
  if ( v4 < 0 )
    return v4 | 0x10000000;
  CloseHandle((HANDLE)i[3]);
  v6 = (__int64 *)*i;
  if ( *(__int64 **)(*i + 8) != i || (v7 = (__int64 **)i[1], *v7 != i) )
    __fastfail(3u);
  *v7 = v6;
  v6[1] = (__int64)v7;
  --*((_DWORD *)this + 10);
  operator delete(i, v5);
  return 0;
}

```

## disassembly

```asm
0x18002aeb0  mov     [rsp+arg_0], rbx
0x18002aeb5  push    rdi
0x18002aeb6  sub     rsp, 20h
0x18002aeba  lea     rax, [rcx+18h]
0x18002aebe  mov     rdi, rcx
0x18002aec1  mov     rbx, [rax]
0x18002aec4  cmp     rbx, rax
0x18002aec7  jz      short loc_18002AF2F
0x18002aec9  cmp     [rbx+10h], rdx
0x18002aecd  jz      short loc_18002AED4
0x18002aecf  mov     rbx, [rbx]
0x18002aed2  jmp     short loc_18002AEC4
0x18002aed4  mov     rcx, [rbx+18h]
0x18002aed8  mov     dl, 1
0x18002aeda  call    cs:__imp_NtCancelWaitCompletionPacket
0x18002aee1  nop     dword ptr [rax+rax+00h]
0x18002aee6  test    eax, eax
0x18002aee8  js      short loc_18002AF29
0x18002aeea  mov     rcx, [rbx+18h]; hObject
0x18002aeee  call    cs:__imp_CloseHandle
0x18002aef5  nop     dword ptr [rax+rax+00h]
0x18002aefa  mov     rcx, [rbx]
0x18002aefd  cmp     [rcx+8], rbx
0x18002af01  jnz     short loc_18002AF22
0x18002af03  mov     rax, [rbx+8]
0x18002af07  cmp     [rax], rbx
0x18002af0a  jnz     short loc_18002AF22
0x18002af0c  mov     [rax], rcx
0x18002af0f  mov     [rcx+8], rax
0x18002af13  mov     rcx, rbx; P
0x18002af16  dec     dword ptr [rdi+28h]
0x18002af19  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18002af1e  xor     eax, eax
0x18002af20  jmp     short loc_18002AF34
0x18002af22  mov     ecx, 3
0x18002af27  int     29h; Win8: RtlFailFast(ecx)
0x18002af29  bts     eax, 1Ch
0x18002af2d  jmp     short loc_18002AF34
0x18002af2f  mov     eax, 0D00002F0h
0x18002af34  mov     rbx, [rsp+28h+arg_0]
0x18002af39  add     rsp, 20h
0x18002af3d  pop     rdi
0x18002af3e  retn
```
