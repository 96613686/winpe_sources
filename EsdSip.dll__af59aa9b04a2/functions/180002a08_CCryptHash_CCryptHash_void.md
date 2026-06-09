# CCryptHash::~CCryptHash(void)

- ea: `0x180002a08`
- end: `0x180002a45`
- name: `??1CCryptHash@@QEAA@XZ`
- size: `61`
- prototype: `void __fastcall(CCryptHash *__hidden this)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x1800019e0`
- `0x180002360`

## callees

- `0x180002a08`

## import_xrefs

- `ADVAPI32!CryptDestroyHash` at `0x180002a25`
- `ADVAPI32!CryptDestroyHash` at `0x180002a25`
- `KERNEL32!SetLastError` at `0x180002a3e`
- `KERNEL32!GetLastError` at `0x180002a15`
- `KERNEL32!GetLastError` at `0x180002a15`

## pseudocode

```c
void __fastcall CCryptHash::~CCryptHash(HCRYPTHASH *this)
{
  DWORD LastError; // edi

  LastError = GetLastError();
  if ( *this )
  {
    CryptDestroyHash(*this);
    *this = 0;
  }
  SetLastError(LastError);
}

```

## disassembly

```asm
0x180002a08  mov     [rsp+arg_0], rbx
0x180002a0d  push    rdi
0x180002a0e  sub     rsp, 20h
0x180002a12  mov     rbx, rcx
0x180002a15  call    cs:__imp_GetLastError
0x180002a1b  mov     rcx, [rbx]; hHash
0x180002a1e  mov     edi, eax
0x180002a20  test    rcx, rcx
0x180002a23  jz      short loc_180002A32
0x180002a25  call    cs:__imp_CryptDestroyHash
0x180002a2b  mov     qword ptr [rbx], 0
0x180002a32  mov     ecx, edi
0x180002a34  mov     rbx, [rsp+28h+arg_0]
0x180002a39  add     rsp, 20h
0x180002a3d  pop     rdi
0x180002a3e  jmp     cs:__imp_SetLastError
```
