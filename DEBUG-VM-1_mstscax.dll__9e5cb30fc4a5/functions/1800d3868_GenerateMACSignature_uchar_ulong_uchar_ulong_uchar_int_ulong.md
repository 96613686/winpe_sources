# GenerateMACSignature(uchar *,ulong,uchar *,ulong,uchar *,int,ulong)

- ea: `0x1800d3868`
- end: `0x1800d3a88`
- name: `?GenerateMACSignature@@YAXPEAEK0K0HK@Z`
- size: `544`
- prototype: `void __usercall(PUCHAR pbInput@<rcx>, unsigned int@<edx>, unsigned __int8 *@<r8>, unsigned int@<r9d>, unsigned __int8 *, int, unsigned int)`
- caller_count: `5`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x18004c580`
- `0x18004efd0`
- `0x18007f6e0`
- `0x1800e73b0`
- `0x18016ec4c`

## callees

- `0x18008ee68`
- `0x1800a363c`
- `0x1800a5c88`
- `0x1800d3868`
- `0x180688fc0`

## import_xrefs

- `bcrypt!BCryptFinishHash` at `0x1800d39a3`
- `bcrypt!BCryptFinishHash` at `0x1800d3a5a`
- `bcrypt!BCryptFinishHash` at `0x1800d39a3`
- `bcrypt!BCryptFinishHash` at `0x1800d3a5a`
- `bcrypt!BCryptHashData` at `0x1800d38c4`
- `bcrypt!BCryptHashData` at `0x1800d38f7`
- `bcrypt!BCryptHashData` at `0x1800d3927`
- `bcrypt!BCryptHashData` at `0x1800d3956`
- `bcrypt!BCryptHashData` at `0x1800d39da`
- `bcrypt!BCryptHashData` at `0x1800d3a07`
- `bcrypt!BCryptHashData` at `0x1800d3a30`
- `bcrypt!BCryptHashData` at `0x1800d38c4`
- `bcrypt!BCryptHashData` at `0x1800d38f7`
- `bcrypt!BCryptHashData` at `0x1800d3927`
- `bcrypt!BCryptHashData` at `0x1800d3956`
- `bcrypt!BCryptHashData` at `0x1800d39da`
- `bcrypt!BCryptHashData` at `0x1800d3a07`
- `bcrypt!BCryptHashData` at `0x1800d3a30`
- `bcrypt!BCryptDestroyHash` at `0x1800d38d2`
- `bcrypt!BCryptDestroyHash` at `0x1800d3905`
- `bcrypt!BCryptDestroyHash` at `0x1800d3935`
- `bcrypt!BCryptDestroyHash` at `0x1800d3964`
- `bcrypt!BCryptDestroyHash` at `0x1800d39ad`
- `bcrypt!BCryptDestroyHash` at `0x1800d39e8`
- `bcrypt!BCryptDestroyHash` at `0x1800d3a15`
- `bcrypt!BCryptDestroyHash` at `0x1800d3a3e`
- `bcrypt!BCryptDestroyHash` at `0x1800d3a64`
- `bcrypt!BCryptDestroyHash` at `0x1800d38d2`
- `bcrypt!BCryptDestroyHash` at `0x1800d3905`
- `bcrypt!BCryptDestroyHash` at `0x1800d3935`
- `bcrypt!BCryptDestroyHash` at `0x1800d3964`
- `bcrypt!BCryptDestroyHash` at `0x1800d39ad`
- `bcrypt!BCryptDestroyHash` at `0x1800d39e8`
- `bcrypt!BCryptDestroyHash` at `0x1800d3a15`
- `bcrypt!BCryptDestroyHash` at `0x1800d3a3e`
- `bcrypt!BCryptDestroyHash` at `0x1800d3a64`

## string_xrefs

- `0x1800d39fc`: `\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\kernel32.dll`

## pseudocode

```c

```
