# VsmUtils::GetClaimSubject(tpm12class::TPMW8T_PUBLIC *,uchar *,uint,tpm12class::TPMW8_Certify *,uchar * *,uint *)

- ea: `0x14005b650`
- end: `0x14005b93d`
- name: `?GetClaimSubject@VsmUtils@@YAJPEAVTPMW8T_PUBLIC@tpm12class@@PEAEIPEAVTPMW8_Certify@3@PEAPEAEPEAI@Z`
- size: `749`
- prototype: `__int64 __usercall@<rax>(VsmUtils *__hidden this@<rcx>, struct tpm12class::TPMW8T_PUBLIC *Src@<rdx>, size_t Size@<r8>, unsigned int@<r9d>, struct tpm12class::TPMW8_Certify *, unsigned __int8 **, unsigned int *)`
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x140056650`

## callees

- `0x140007410`
- `0x14000e034`
- `0x1400104fc`
- `0x140055164`
- `0x14005b650`
- `0x140061fb0`
- `0x1400676b4`

## import_xrefs

- `api-ms-win-core-heap-obsolete-l1-1-0!LocalFree` at `0x14005b7b1`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalFree` at `0x14005b7b1`

## string_xrefs

- `0x14005b698`: `onecore\ds\security\trustlet\utils\vtl1\lib\tpmhelper.cpp`
- `0x14005b71b`: `onecore\ds\security\trustlet\utils\vtl1\lib\tpmhelper.cpp`
- `0x14005b78e`: `onecore\ds\security\trustlet\utils\vtl1\lib\tpmhelper.cpp`
- `0x14005b8ba`: `onecore\ds\security\trustlet\utils\vtl1\lib\tpmhelper.cpp`

## pseudocode

```c

```
