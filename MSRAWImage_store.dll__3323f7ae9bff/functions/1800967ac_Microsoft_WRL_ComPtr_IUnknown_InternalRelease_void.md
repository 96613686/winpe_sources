# Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)

- ea: `0x1800967ac`
- end: `0x1800967d2`
- name: `?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ`
- size: `38`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `17`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180095a74`
- `0x180095b1c`
- `0x180095bb0`
- `0x180095be0`
- `0x1800985cc`
- `0x1800985f4`
- `0x180098650`
- `0x180098684`
- `0x1800986cc`
- `0x18009874c`
- `0x180098840`
- `0x1800997d0`
- `0x18009c120`
- `0x1800a25b8`
- `0x1800a5284`
- `0x1800a5344`
- `0x1800a57b0`

## callees

- `0x1800967ac`
- `0x1800b4010`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(__int64 *a1)
{
  __int64 result; // rax
  __int64 v3; // rcx

  result = 0;
  v3 = *a1;
  if ( v3 )
  {
    *a1 = 0;
    return (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v3 + 16LL))(v3);
  }
  return result;
}

```

## disassembly

```asm
0x1800967ac  sub     rsp, 28h
0x1800967b0  mov     rdx, rcx
0x1800967b3  xor     eax, eax
0x1800967b5  mov     rcx, [rcx]
0x1800967b8  test    rcx, rcx
0x1800967bb  jz      short loc_1800967CC
0x1800967bd  mov     [rdx], rax
0x1800967c0  mov     rax, [rcx]
0x1800967c3  mov     rax, [rax+10h]
0x1800967c7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800967cc  add     rsp, 28h
0x1800967d0  retn
```
