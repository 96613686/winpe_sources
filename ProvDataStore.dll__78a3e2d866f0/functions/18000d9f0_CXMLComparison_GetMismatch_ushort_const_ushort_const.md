# CXMLComparison::GetMismatch(ushort const * *,ushort const * *)

- ea: `0x18000d9f0`
- end: `0x18000da13`
- name: `?GetMismatch@CXMLComparison@@UEBAXPEAPEBG0@Z`
- size: `35`
- prototype: `void __fastcall(CXMLComparison *__hidden this, const unsigned __int16 **, const unsigned __int16 **)`
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callees

- `0x18000d9f0`

## pseudocode

```c
void __fastcall CXMLComparison::GetMismatch(
        CXMLComparison *this,
        const unsigned __int16 **a2,
        const unsigned __int16 **a3)
{
  const unsigned __int16 *v3; // rax
  const unsigned __int16 *v4; // rax

  v3 = (const unsigned __int16 *)((char *)this + 16);
  if ( *((_QWORD *)this + 5) >= 8u )
    v3 = *(const unsigned __int16 **)v3;
  *a2 = v3;
  v4 = (const unsigned __int16 *)((char *)this + 48);
  if ( *((_QWORD *)this + 9) >= 8u )
    v4 = *(const unsigned __int16 **)v4;
  *a3 = v4;
}

```

## disassembly

```asm
0x18000d9f0  lea     rax, [rcx+10h]
0x18000d9f4  cmp     qword ptr [rax+18h], 8
0x18000d9f9  jb      short loc_18000D9FE
0x18000d9fb  mov     rax, [rax]
0x18000d9fe  mov     [rdx], rax
0x18000da01  lea     rax, [rcx+30h]
0x18000da05  cmp     qword ptr [rax+18h], 8
0x18000da0a  jb      short loc_18000DA0F
0x18000da0c  mov     rax, [rax]
0x18000da0f  mov     [r8], rax
0x18000da12  retn
```
