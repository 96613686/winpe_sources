# ATL::CComContainedObject<CIdentityStore>::`vector deleting destructor'(uint)

- ea: `0x180010ad0`
- end: `0x180010b00`
- name: `??_E?$CComContainedObject@VCIdentityStore@@@ATL@@UEAAPEAXI@Z`
- size: `48`
- prototype: `CIdentityStore *__fastcall(CIdentityStore *, __int64, __int64)`
- caller_count: `0`
- callee_count: `2`
- tags: `file_ops, broker_com_uri`

## callees

- `0x18000afb0`
- `0x180010ad0`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x180010aec`
- `msvcrt!??3@YAXPEAX@Z` at `0x180010aec`

## pseudocode

```c
CIdentityStore *__fastcall ATL::CComContainedObject<CIdentityStore>::`vector deleting destructor'(
        CIdentityStore *a1,
        __int64 a2,
        __int64 a3)
{
  char v3; // bl

  v3 = a2;
  CIdentityStore::~CIdentityStore(a1, a2, a3);
  if ( (v3 & 1) != 0 )
    operator delete(a1);
  return a1;
}

```

## disassembly

```asm
0x180010ad0  mov     [rsp+arg_0], rbx
0x180010ad5  push    rdi
0x180010ad6  sub     rsp, 20h
0x180010ada  mov     ebx, edx
0x180010adc  mov     rdi, rcx
0x180010adf  call    ??1CIdentityStore@@UEAA@XZ; CIdentityStore::~CIdentityStore(void)
0x180010ae4  test    bl, 1
0x180010ae7  jz      short loc_180010AF2
0x180010ae9  mov     rcx, rdi
0x180010aec  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180010af2  mov     rbx, [rsp+28h+arg_0]
0x180010af7  mov     rax, rdi
0x180010afa  add     rsp, 20h
0x180010afe  pop     rdi
0x180010aff  retn
```
