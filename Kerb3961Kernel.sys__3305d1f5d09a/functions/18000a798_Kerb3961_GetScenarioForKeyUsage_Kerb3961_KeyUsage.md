# Kerb3961::GetScenarioForKeyUsage(Kerb3961::KeyUsage)

- ea: `0x18000a798`
- end: `0x18000a805`
- name: `?GetScenarioForKeyUsage@Kerb3961@@YA?AV?$optional@UKeyPolicyScenario@Kerb3961@@@utl@@W4KeyUsage@1@@Z`
- size: `109`
- prototype: ``
- caller_count: `7`
- callee_count: `1`
- tags: ``

## callers

- `0x18000ba20`
- `0x18000bbc0`
- `0x18000c000`
- `0x18000c580`
- `0x18000c710`
- `0x18000cbd0`
- `0x18000cd60`

## callees

- `0x18000a798`

## pseudocode

```c
__int64 __fastcall Kerb3961::GetScenarioForKeyUsage(__int64 a1, unsigned __int64 a2)
{
  _QWORD *v3; // rax
  _DWORD *v4; // r8
  __int64 v5; // rdx
  char v6; // al

  if ( (_UNKNOWN *)qword_18001A328 == &Kerb3961::g_keyUsageMap )
    goto LABEL_10;
  v3 = (_QWORD *)Kerb3961::g_keyUsageMap;
  v4 = &Kerb3961::g_keyUsageMap;
  do
  {
    if ( v3[3] >= a2 )
    {
      v4 = v3;
      v5 = 1;
    }
    else
    {
      v5 = 2;
    }
    v3 = (_QWORD *)v3[v5];
  }
  while ( v3 != (_QWORD *)&utl::_TreeSentinel );
  if ( v4 == (_DWORD *)&Kerb3961::g_keyUsageMap || a2 < *((_QWORD *)v4 + 3) )
  {
LABEL_10:
    v6 = 0;
    *(_DWORD *)a1 = 0;
    *(_WORD *)(a1 + 4) = 0;
  }
  else
  {
    *(_DWORD *)a1 = v4[8];
    *(_BYTE *)(a1 + 4) = *((_BYTE *)v4 + 36);
    v6 = 1;
  }
  *(_BYTE *)(a1 + 5) = v6;
  return a1;
}

```

## disassembly

```asm
0x18000a798  lea     r10, ?g_keyUsageMap@Kerb3961@@3UKeyUsageMap@1@A; Kerb3961::KeyUsageMap Kerb3961::g_keyUsageMap
0x18000a79f  mov     r9, rdx
0x18000a7a2  cmp     cs:qword_18001A328, r10
0x18000a7a9  jz      short loc_18000A7F6
0x18000a7ab  mov     rax, cs:?g_keyUsageMap@Kerb3961@@3UKeyUsageMap@1@A; Kerb3961::KeyUsageMap Kerb3961::g_keyUsageMap
0x18000a7b2  mov     r8, r10
0x18000a7b5  cmp     [rax+18h], r9
0x18000a7b9  jnb     short loc_18000A7C2
0x18000a7bb  mov     edx, 10h
0x18000a7c0  jmp     short loc_18000A7CA
0x18000a7c2  mov     r8, rax
0x18000a7c5  mov     edx, 8
0x18000a7ca  mov     rax, [rdx+rax]
0x18000a7ce  lea     rdx, ?_TreeSentinel@utl@@3PEAXEA; void * utl::_TreeSentinel
0x18000a7d5  cmp     rax, rdx
0x18000a7d8  jnz     short loc_18000A7B5
0x18000a7da  cmp     r8, r10
0x18000a7dd  jz      short loc_18000A7F6
0x18000a7df  cmp     r9, [r8+18h]
0x18000a7e3  jb      short loc_18000A7F6
0x18000a7e5  mov     eax, [r8+20h]
0x18000a7e9  mov     [rcx], eax
0x18000a7eb  mov     al, [r8+24h]
0x18000a7ef  mov     [rcx+4], al
0x18000a7f2  mov     al, 1
0x18000a7f4  jmp     short loc_18000A7FE
0x18000a7f6  xor     eax, eax
0x18000a7f8  mov     [rcx], eax
0x18000a7fa  mov     [rcx+4], ax
0x18000a7fe  mov     [rcx+5], al
0x18000a801  mov     rax, rcx
0x18000a804  retn
```
