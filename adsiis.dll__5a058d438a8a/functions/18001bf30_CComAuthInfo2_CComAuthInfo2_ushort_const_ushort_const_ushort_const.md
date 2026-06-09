# CComAuthInfo2::CComAuthInfo2(ushort const *,ushort const *,ushort const *)

- ea: `0x18001bf30`
- end: `0x18001bf8e`
- name: `??0CComAuthInfo2@@QEAA@PEBG00@Z`
- size: `94`
- prototype: `CComAuthInfo2 *__fastcall(CComAuthInfo2 *__hidden this, const unsigned __int16 *, OLECHAR *psz, OLECHAR *)`
- caller_count: `2`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180013430`
- `0x18001a578`

## callees

- `0x18001c398`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x18001bf52`
- `OLEAUT32!__imp_SysAllocString` at `0x18001bf5f`
- `OLEAUT32!__imp_SysAllocString` at `0x18001bf52`
- `OLEAUT32!__imp_SysAllocString` at `0x18001bf5f`

## pseudocode

```c
CComAuthInfo2 *__fastcall CComAuthInfo2::CComAuthInfo2(
        CComAuthInfo2 *this,
        const unsigned __int16 *a2,
        OLECHAR *psz,
        OLECHAR *a4)
{
  *(_QWORD *)this = 0;
  *((_QWORD *)this + 1) = SysAllocString(psz);
  *((_QWORD *)this + 2) = SysAllocString(a4);
  *((_DWORD *)this + 6) = 0;
  CComAuthInfo2::SetComputerNameW(this, a2);
  return this;
}

```

## disassembly

```asm
0x18001bf30  mov     [rsp+arg_0], rbx
0x18001bf35  mov     [rsp+arg_8], rsi
0x18001bf3a  push    rdi
0x18001bf3b  sub     rsp, 20h
0x18001bf3f  mov     rsi, rcx
0x18001bf42  mov     qword ptr [rcx], 0
0x18001bf49  mov     rcx, r8; psz
0x18001bf4c  mov     rbx, r9
0x18001bf4f  mov     rdi, rdx
0x18001bf52  call    cs:__imp_SysAllocString
0x18001bf58  mov     rcx, rbx; psz
0x18001bf5b  mov     [rsi+8], rax
0x18001bf5f  call    cs:__imp_SysAllocString
0x18001bf65  mov     [rsi+10h], rax
0x18001bf69  mov     rdx, rdi; unsigned __int16 *
0x18001bf6c  mov     rcx, rsi; this
0x18001bf6f  mov     dword ptr [rsi+18h], 0
0x18001bf76  call    ?SetComputerNameW@CComAuthInfo2@@IEAAXPEBG@Z; CComAuthInfo2::SetComputerNameW(ushort const *)
0x18001bf7b  mov     rbx, [rsp+28h+arg_0]
0x18001bf80  mov     rax, rsi
0x18001bf83  mov     rsi, [rsp+28h+arg_8]
0x18001bf88  add     rsp, 20h
0x18001bf8c  pop     rdi
0x18001bf8d  retn
```
