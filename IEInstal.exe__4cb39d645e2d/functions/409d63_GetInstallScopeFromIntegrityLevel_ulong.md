# GetInstallScopeFromIntegrityLevel(ulong *)

- ea: `0x409d63`
- end: `0x409db6`
- name: `?GetInstallScopeFromIntegrityLevel@@YGJPAK@Z`
- size: `83`
- prototype: `int __thiscall(int *this)`
- caller_count: `2`
- callee_count: `1`
- tags: `installer_update, broker_com_uri`

## callers

- `0x40784b`
- `0x409dbc`

## callees

- `0x409d63`

## import_xrefs

- `iertutil!__imp_?GetProcessIntegrityLevel@@YGJPAXPAK@Z` at `0x409d78`
- `iertutil!__imp_?GetProcessIntegrityLevel@@YGJPAXPAK@Z` at `0x409d78`

## pseudocode

```c
int __thiscall GetInstallScopeFromIntegrityLevel(int *this)
{
  int ProcessIntegrityLevel; // ecx
  int v3; // eax
  unsigned int v5; // [esp+4h] [ebp-4h] BYREF

  *this = 0;
  ProcessIntegrityLevel = GetProcessIntegrityLevel(0, &v5);
  if ( ProcessIntegrityLevel )
  {
    v3 = 1;
    if ( ProcessIntegrityLevel != 1 )
      return ProcessIntegrityLevel;
    ProcessIntegrityLevel = 0;
LABEL_7:
    *this = v3;
    return ProcessIntegrityLevel;
  }
  if ( v5 < 0x3000 )
  {
    v3 = v5 < 0x2000 ? 0 : 2;
    goto LABEL_7;
  }
  *this = 1;
  return ProcessIntegrityLevel;
}

```

## disassembly

```asm
0x409d63  mov     edi, edi
0x409d65  push    ebp
0x409d66  mov     ebp, esp
0x409d68  push    ecx
0x409d69  push    esi
0x409d6a  mov     esi, ecx
0x409d6c  lea     eax, [ebp+var_4]
0x409d6f  push    eax
0x409d70  push    0
0x409d72  mov     dword ptr [esi], 0
0x409d78  call    ds:__imp_?GetProcessIntegrityLevel@@YGJPAXPAK@Z; GetProcessIntegrityLevel(void *,ulong *)
0x409d7e  mov     ecx, eax
0x409d80  test    ecx, ecx
0x409d82  jnz     short loc_409DA6
0x409d84  cmp     [ebp+var_4], 3000h
0x409d8b  jb      short loc_409D95
0x409d8d  mov     dword ptr [esi], 1
0x409d93  jmp     short loc_409DB1
0x409d95  cmp     [ebp+var_4], 2000h
0x409d9c  sbb     eax, eax
0x409d9e  and     eax, 0FFFFFFFEh
0x409da1  add     eax, 2
0x409da4  jmp     short loc_409DAF
0x409da6  xor     eax, eax
0x409da8  inc     eax
0x409da9  cmp     ecx, eax
0x409dab  jnz     short loc_409DB1
0x409dad  xor     ecx, ecx
0x409daf  mov     [esi], eax
0x409db1  mov     eax, ecx
0x409db3  pop     esi
0x409db4  leave
0x409db5  retn
```
