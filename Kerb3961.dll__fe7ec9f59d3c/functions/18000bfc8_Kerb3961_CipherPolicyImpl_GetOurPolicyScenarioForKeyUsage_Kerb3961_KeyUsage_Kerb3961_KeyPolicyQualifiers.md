# Kerb3961::CipherPolicyImpl::GetOurPolicyScenarioForKeyUsage(Kerb3961::KeyUsage,Kerb3961::KeyPolicyQualifiers)

- ea: `0x18000bfc8`
- end: `0x18000c04b`
- name: `?GetOurPolicyScenarioForKeyUsage@CipherPolicyImpl@Kerb3961@@QEBA?AV?$optional@UKeyPolicyScenario@Kerb3961@@@utl@@W4KeyUsage@2@W4KeyPolicyQualifiers@2@@Z`
- size: `131`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `12`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x18000b024`
- `0x18000b300`
- `0x18000b3d0`
- `0x18000ba20`
- `0x18000bcd0`
- `0x18000c060`
- `0x18000cdb0`
- `0x18000cfd0`
- `0x18000d510`
- `0x18000d6e0`
- `0x18000d960`
- `0x18000db90`

## callees

- `0x18000bfc8`

## pseudocode

```c
__int64 __fastcall Kerb3961::CipherPolicyImpl::GetOurPolicyScenarioForKeyUsage(
        __int64 a1,
        __int64 a2,
        unsigned __int64 a3,
        char a4)
{
  void **v5; // rax
  void **v6; // r10
  __int64 v7; // rcx
  char v8; // al
  char v9; // al

  if ( (_UNKNOWN *)qword_180029278 == &Kerb3961::g_keyUsageMap )
    goto LABEL_10;
  v5 = (void **)Kerb3961::g_keyUsageMap;
  v6 = (void **)&Kerb3961::g_keyUsageMap;
  do
  {
    if ( (unsigned __int64)v5[3] >= a3 )
    {
      v6 = v5;
      v7 = 1;
    }
    else
    {
      v7 = 2;
    }
    v5 = (void **)v5[v7];
  }
  while ( v5 != &utl::_TreeSentinel );
  if ( v6 == (void **)&Kerb3961::g_keyUsageMap || a3 < (unsigned __int64)v6[3] )
  {
LABEL_10:
    *(_DWORD *)a2 = 0;
    *(_WORD *)(a2 + 4) = 0;
    *(_BYTE *)(a2 + 5) = 0;
  }
  else
  {
    *(_DWORD *)a2 = *((_DWORD *)v6 + 8);
    v8 = *((_BYTE *)v6 + 36);
    *(_BYTE *)(a2 + 5) = 1;
    v9 = a4 | v8;
    *(_BYTE *)(a2 + 4) = v9;
    *(_BYTE *)(a2 + 4) = *(_BYTE *)(a1 + 12) | v9;
  }
  return a2;
}

```

## disassembly

```asm
0x18000bfc8  mov     [rsp+arg_0], rbx
0x18000bfcd  lea     rbx, ?g_keyUsageMap@Kerb3961@@3UKeyUsageMap@1@A; Kerb3961::KeyUsageMap Kerb3961::g_keyUsageMap
0x18000bfd4  mov     r11, rcx
0x18000bfd7  cmp     cs:qword_180029278, rbx
0x18000bfde  jz      short loc_18000C037
0x18000bfe0  mov     rax, cs:?g_keyUsageMap@Kerb3961@@3UKeyUsageMap@1@A; Kerb3961::KeyUsageMap Kerb3961::g_keyUsageMap
0x18000bfe7  mov     r10, rbx
0x18000bfea  cmp     [rax+18h], r8
0x18000bfee  jnb     short loc_18000BFF7
0x18000bff0  mov     ecx, 10h
0x18000bff5  jmp     short loc_18000BFFF
0x18000bff7  mov     r10, rax
0x18000bffa  mov     ecx, 8
0x18000bfff  mov     rax, [rcx+rax]
0x18000c003  lea     rcx, ?_TreeSentinel@utl@@3PEAXEA; void * utl::_TreeSentinel
0x18000c00a  cmp     rax, rcx
0x18000c00d  jnz     short loc_18000BFEA
0x18000c00f  cmp     r10, rbx
0x18000c012  jz      short loc_18000C037
0x18000c014  cmp     r8, [r10+18h]
0x18000c018  jb      short loc_18000C037
0x18000c01a  mov     eax, [r10+20h]
0x18000c01e  mov     [rdx], eax
0x18000c020  mov     al, [r10+24h]
0x18000c024  mov     byte ptr [rdx+5], 1
0x18000c028  or      al, r9b
0x18000c02b  mov     [rdx+4], al
0x18000c02e  or      al, [r11+0Ch]
0x18000c032  mov     [rdx+4], al
0x18000c035  jmp     short loc_18000C042
0x18000c037  xor     eax, eax
0x18000c039  mov     [rdx], eax
0x18000c03b  mov     [rdx+4], ax
0x18000c03f  mov     [rdx+5], al
0x18000c042  mov     rbx, [rsp+arg_0]
0x18000c047  mov     rax, rdx
0x18000c04a  retn
```
