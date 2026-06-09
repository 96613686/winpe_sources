# Comms::CalculateSize::CopyBytesIn(void const *,unsigned __int64,type_info const &)

- ea: `0x1800038f0`
- end: `0x180003922`
- name: `?CopyBytesIn@CalculateSize@Comms@@UEAAXPEBX_KAEBVtype_info@@@Z`
- size: `50`
- prototype: `void __fastcall(Comms::CalculateSize *this, const void *, __int64, const struct type_info *)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x1800038f0`

## import_xrefs

- `msvcrt!?raw_name@type_info@@QEBAPEBDXZ` at `0x18000390a`
- `msvcrt!?raw_name@type_info@@QEBAPEBDXZ` at `0x18000390a`

## pseudocode

```c
void __fastcall Comms::CalculateSize::CopyBytesIn(
        Comms::CalculateSize *this,
        const void *a2,
        __int64 a3,
        const struct type_info *a4)
{
  _QWORD *v4; // rbx

  v4 = (_QWORD *)((char *)this + 8);
  if ( *((_BYTE *)this + 16) )
  {
    type_info::raw_name(a4);
    *v4 += 4LL;
  }
  *v4 += a3;
}

```

## disassembly

```asm
0x1800038f0  mov     [rsp+arg_0], rbx
0x1800038f5  push    rdi
0x1800038f6  sub     rsp, 20h
0x1800038fa  cmp     byte ptr [rcx+10h], 0
0x1800038fe  lea     rbx, [rcx+8]
0x180003902  mov     rdi, r8
0x180003905  jz      short loc_180003914
0x180003907  mov     rcx, r9
0x18000390a  call    cs:__imp_?raw_name@type_info@@QEBAPEBDXZ; type_info::raw_name(void)
0x180003910  add     qword ptr [rbx], 4
0x180003914  add     [rbx], rdi
0x180003917  mov     rbx, [rsp+28h+arg_0]
0x18000391c  add     rsp, 20h
0x180003920  pop     rdi
0x180003921  retn
```
