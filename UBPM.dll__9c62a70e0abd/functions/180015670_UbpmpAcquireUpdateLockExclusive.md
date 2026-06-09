# UbpmpAcquireUpdateLockExclusive

- ea: `0x180015670`
- end: `0x1800156e7`
- name: `UbpmpAcquireUpdateLockExclusive`
- size: `119`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting, installer_update`

## callers

- `0x1800136b0`

## callees

- `0x180015670`

## import_xrefs

- `ntdll!RtlAcquireSRWLockExclusive` at `0x1800156b9`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x1800156b9`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180015687`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180015698`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180015687`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180015698`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800156c5`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800156c5`

## pseudocode

```c
DWORD UbpmpAcquireUpdateLockExclusive()
{
  DWORD v0; // edi
  _QWORD *Value; // rbx
  DWORD result; // eax

  v0 = UbpmpLockTrackerId;
  if ( UbpmpLockTrackerId != -1 )
  {
    Value = TlsGetValue(UbpmpLockTrackerId);
    if ( *(_QWORD *)TlsGetValue(v0) )
      __int2c();
    *Value |= 1uLL;
    ++Value[1];
  }
  RtlAcquireSRWLockExclusive(&g_ConsumerUpdateLock);
  result = GetCurrentThreadId();
  dword_18004FFC8 = result;
  return result;
}

```

## disassembly

```asm
0x180015670  mov     [rsp+arg_0], rbx
0x180015675  push    rdi
0x180015676  sub     rsp, 20h
0x18001567a  mov     edi, cs:UbpmpLockTrackerId
0x180015680  cmp     edi, 0FFFFFFFFh
0x180015683  jz      short loc_1800156B2
0x180015685  mov     ecx, edi; dwTlsIndex
0x180015687  call    cs:__imp_TlsGetValue
0x18001568e  nop     dword ptr [rax+rax+00h]
0x180015693  mov     ecx, edi; dwTlsIndex
0x180015695  mov     rbx, rax
0x180015698  call    cs:__imp_TlsGetValue
0x18001569f  nop     dword ptr [rax+rax+00h]
0x1800156a4  cmp     qword ptr [rax], 0
0x1800156a8  jnz     short loc_1800156E3
0x1800156aa  or      qword ptr [rbx], 1
0x1800156ae  inc     qword ptr [rbx+8]
0x1800156b2  lea     rcx, ?g_ConsumerUpdateLock@@3U_CEM_LOCK@@A; _CEM_LOCK g_ConsumerUpdateLock
0x1800156b9  call    cs:__imp_RtlAcquireSRWLockExclusive
0x1800156c0  nop     dword ptr [rax+rax+00h]
0x1800156c5  call    cs:__imp_GetCurrentThreadId
0x1800156cc  nop     dword ptr [rax+rax+00h]
0x1800156d1  mov     rbx, [rsp+28h+arg_0]
0x1800156d6  mov     cs:dword_18004FFC8, eax
0x1800156dc  add     rsp, 20h
0x1800156e0  pop     rdi
0x1800156e1  retn
0x1800156e3  int     2Ch; Windows NT - assertion failure
0x1800156e5  jmp     short loc_1800156AA
```
