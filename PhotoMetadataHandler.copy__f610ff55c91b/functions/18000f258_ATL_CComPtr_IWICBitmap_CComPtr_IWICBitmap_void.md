# ATL::CComPtr<IWICBitmap>::~CComPtr<IWICBitmap>(void)

- ea: `0x18000f258`
- end: `0x18000f276`
- name: `??1?$CComPtr@UIWICBitmap@@@ATL@@QEAA@XZ`
- size: `30`
- prototype: ``
- caller_count: `24`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180026520`
- `0x1800267f2`
- `0x18002680b`
- `0x180026860`
- `0x180026880`
- `0x1800268f0`
- `0x180026910`
- `0x180026970`
- `0x180026990`
- `0x1800269b0`
- `0x1800269e2`
- `0x1800269f4`
- `0x180026c1d`
- `0x180026ce6`
- `0x180026cf8`
- `0x180026d0a`
- `0x180026d1c`
- `0x180026d2e`
- `0x180026d40`
- `0x180026d52`
- `0x180026d64`
- `0x180026d76`
- `0x180027061`
- `0x1800270df`

## callees

- `0x18000f258`
- `0x180028010`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall ATL::CComPtr<IWICBitmap>::~CComPtr<IWICBitmap>(__int64 *a1)
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
0x18000f258  sub     rsp, 28h
0x18000f25c  mov     rcx, [rcx]
0x18000f25f  test    rcx, rcx
0x18000f262  jz      short loc_18000F271
0x18000f264  mov     rax, [rcx]
0x18000f267  mov     rax, [rax+10h]
0x18000f26b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f270  nop
0x18000f271  add     rsp, 28h
0x18000f275  retn
```
