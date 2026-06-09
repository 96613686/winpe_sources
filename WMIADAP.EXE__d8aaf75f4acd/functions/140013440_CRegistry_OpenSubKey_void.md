# CRegistry::OpenSubKey(void)

- ea: `0x140013440`
- end: `0x1400134a6`
- name: `?OpenSubKey@CRegistry@@AEAAKXZ`
- size: `102`
- prototype: `__int64 __fastcall(CRegistry *this)`
- caller_count: `4`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x140012c00`
- `0x140012e00`
- `0x140012e50`
- `0x140012ea0`

## callees

- `0x14000ff40`
- `0x140012d30`
- `0x140013440`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x140013487`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x140013487`

## pseudocode

```c
__int64 __fastcall CRegistry::OpenSubKey(CRegistry *this)
{
  HKEY *phkResult; // rdi
  unsigned int v3; // ebx
  LPCWSTR lpSubKey; // [rsp+40h] [rbp+8h] BYREF

  lpSubKey = afxPchNil;
  phkResult = (HKEY *)((char *)this + 16);
  if ( *((_QWORD *)this + 2) )
  {
    v3 = 0;
  }
  else
  {
    CRegistry::GetCurrentSubKeyPath(this, (struct CHString *)&lpSubKey);
    v3 = RegOpenKeyExW(*(HKEY *)this, lpSubKey, 0, 0x20019u, phkResult);
  }
  CHString::~CHString(&lpSubKey);
  return v3;
}

```

## disassembly

```asm
0x140013440  mov     [rsp+arg_8], rbx
0x140013445  push    rdi
0x140013446  sub     rsp, 30h
0x14001344a  mov     rbx, rcx
0x14001344d  mov     rax, cs:?afxPchNil@@3PEBGEB; ushort const * const afxPchNil
0x140013454  mov     [rsp+38h+lpSubKey], rax
0x140013459  lea     rdi, [rcx+10h]
0x14001345d  cmp     qword ptr [rdi], 0
0x140013461  jz      short loc_140013467
0x140013463  xor     ebx, ebx
0x140013465  jmp     short loc_14001348F
0x140013467  lea     rdx, [rsp+38h+lpSubKey]; struct CHString *
0x14001346c  call    ?GetCurrentSubKeyPath@CRegistry@@QEAAKAEAVCHString@@@Z; CRegistry::GetCurrentSubKeyPath(CHString &)
0x140013471  mov     [rsp+38h+phkResult], rdi; phkResult
0x140013476  mov     r9d, 20019h; samDesired
0x14001347c  xor     r8d, r8d; ulOptions
0x14001347f  mov     rdx, [rsp+38h+lpSubKey]; lpSubKey
0x140013484  mov     rcx, [rbx]; hKey
0x140013487  call    cs:__imp_RegOpenKeyExW
0x14001348d  mov     ebx, eax
0x14001348f  lea     rcx, [rsp+38h+lpSubKey]; this
0x140013494  call    ??1CHString@@QEAA@XZ; CHString::~CHString(void)
0x140013499  mov     eax, ebx
0x14001349b  mov     rbx, [rsp+38h+arg_8]
0x1400134a0  add     rsp, 30h
0x1400134a4  pop     rdi
0x1400134a5  retn
```
