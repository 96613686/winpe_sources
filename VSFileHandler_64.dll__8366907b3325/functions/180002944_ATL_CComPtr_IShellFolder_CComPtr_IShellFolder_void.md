# ATL::CComPtr<IShellFolder>::~CComPtr<IShellFolder>(void)

- ea: `0x180002944`
- end: `0x18000295c`
- name: `??1?$CComPtr@UIShellFolder@@@ATL@@QEAA@XZ`
- size: `24`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180024d30`

## callees

- `0x180002944`

## pseudocode

```c
__int64 __fastcall ATL::CComPtr<IShellFolder>::~CComPtr<IShellFolder>(__int64 *a1)
{
  __int64 v1; // rcx
  __int64 result; // rax

  v1 = *a1;
  if ( v1 )
    return (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v1 + 16LL))(v1);
  return result;
}

```

## disassembly

```asm
0x180002944  sub     rsp, 28h
0x180002948  mov     rcx, [rcx]
0x18000294b  test    rcx, rcx
0x18000294e  jz      short loc_180002957
0x180002950  mov     rax, [rcx]
0x180002953  call    qword ptr [rax+10h]
0x180002956  nop
0x180002957  add     rsp, 28h
0x18000295b  retn
```
