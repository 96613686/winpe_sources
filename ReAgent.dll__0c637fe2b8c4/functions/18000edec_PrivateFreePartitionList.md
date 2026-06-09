# PrivateFreePartitionList

- ea: `0x18000edec`
- end: `0x18000ee77`
- name: `PrivateFreePartitionList`
- size: `139`
- prototype: `__int64 __fastcall(LPVOID pv)`
- caller_count: `12`
- callee_count: `1`
- tags: `service_task`

## callers

- `0x180004980`
- `0x18000f044`
- `0x180010010`
- `0x1800106d4`
- `0x1800193e8`
- `0x180019a90`
- `0x1800224f0`
- `0x180025a60`
- `0x180026158`
- `0x18002a570`
- `0x18002d88c`
- `0x180036c38`

## callees

- `0x18000edec`

## import_xrefs

- `KERNEL32!TlsSetValue` at `0x18000ee66`
- `KERNEL32!TlsSetValue` at `0x18000ee66`
- `KERNEL32!TlsGetValue` at `0x18000ee06`
- `KERNEL32!TlsGetValue` at `0x18000ee06`
- `ole32!CoTaskMemFree` at `0x18000ee41`
- `ole32!CoTaskMemFree` at `0x18000ee53`
- `ole32!CoTaskMemFree` at `0x18000ee41`
- `ole32!CoTaskMemFree` at `0x18000ee53`

## pseudocode

```c
void __fastcall PrivateFreePartitionList(_QWORD **pv)
{
  _QWORD **Value; // rbx
  _QWORD *v3; // rcx
  _QWORD *v4; // rax

  Value = 0;
  if ( g_TlsIndex != -1 )
    Value = (_QWORD **)TlsGetValue(g_TlsIndex);
  if ( pv )
  {
    if ( pv == Value )
      return;
    Value = pv;
  }
  else if ( !Value )
  {
    return;
  }
  while ( 1 )
  {
    v3 = *Value;
    if ( *Value == Value )
      break;
    if ( (_QWORD **)v3[1] != Value || (v4 = (_QWORD *)*v3, *(_QWORD **)(*v3 + 8LL) != v3) )
      __fastfail(3u);
    *Value = v4;
    v4[1] = Value;
    CoTaskMemFree(v3);
  }
  CoTaskMemFree(Value);
  if ( !pv )
    TlsSetValue(g_TlsIndex, 0);
}

```

## disassembly

```asm
0x18000edec  mov     [rsp+arg_0], rbx
0x18000edf1  push    rdi
0x18000edf2  sub     rsp, 20h
0x18000edf6  mov     rdi, rcx
0x18000edf9  xor     ebx, ebx
0x18000edfb  mov     ecx, cs:g_TlsIndex; dwTlsIndex
0x18000ee01  cmp     ecx, 0FFFFFFFFh
0x18000ee04  jz      short loc_18000EE0F
0x18000ee06  call    cs:__imp_TlsGetValue
0x18000ee0c  mov     rbx, rax
0x18000ee0f  test    rdi, rdi
0x18000ee12  jz      short loc_18000EE1E
0x18000ee14  cmp     rdi, rbx
0x18000ee17  jz      short loc_18000EE6C
0x18000ee19  mov     rbx, rdi
0x18000ee1c  jmp     short loc_18000EE23
0x18000ee1e  test    rbx, rbx
0x18000ee21  jz      short loc_18000EE6C
0x18000ee23  mov     rcx, [rbx]; pv
0x18000ee26  cmp     rcx, rbx
0x18000ee29  jz      short loc_18000EE50
0x18000ee2b  cmp     [rcx+8], rbx
0x18000ee2f  jnz     short loc_18000EE49
0x18000ee31  mov     rax, [rcx]
0x18000ee34  cmp     [rax+8], rcx
0x18000ee38  jnz     short loc_18000EE49
0x18000ee3a  mov     [rbx], rax
0x18000ee3d  mov     [rax+8], rbx
0x18000ee41  call    cs:__imp_CoTaskMemFree
0x18000ee47  jmp     short loc_18000EE23
0x18000ee49  mov     ecx, 3
0x18000ee4e  int     29h; Win8: RtlFailFast(ecx)
0x18000ee50  mov     rcx, rbx; pv
0x18000ee53  call    cs:__imp_CoTaskMemFree
0x18000ee59  test    rdi, rdi
0x18000ee5c  jnz     short loc_18000EE6C
0x18000ee5e  mov     ecx, cs:g_TlsIndex; dwTlsIndex
0x18000ee64  xor     edx, edx; lpTlsValue
0x18000ee66  call    cs:__imp_TlsSetValue
0x18000ee6c  mov     rbx, [rsp+28h+arg_0]
0x18000ee71  add     rsp, 20h
0x18000ee75  pop     rdi
0x18000ee76  retn
```
