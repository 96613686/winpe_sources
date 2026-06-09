# ZtHelperInitClientCerts

- ea: `0x180009420`
- end: `0x18000954e`
- name: `ZtHelperInitClientCerts`
- size: `302`
- prototype: `__int64 __fastcall(unsigned int, __int64, __int64)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, installer_update`

## callers

- `0x18000376c`

## callees

- `0x180008e40`
- `0x180009420`
- `0x18000dbcc`
- `0x180012410`
- `0x180015008`
- `0x180015040`

## import_xrefs

- `DNSAPI!DnsFreeZtClientCertConfig` at `0x18000950b`
- `DNSAPI!DnsFreeZtClientCertConfig` at `0x18000950b`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800094f0`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800094f0`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180009486`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180009486`

## pseudocode

```c
__int64 __fastcall ZtHelperInitClientCerts(unsigned int a1, __int64 a2, __int64 a3)
{
  LPVOID *v5; // rcx
  unsigned int v7; // ebx
  int updated; // eax
  USHORT v9; // dx
  LPVOID lpMem; // [rsp+48h] [rbp+10h] BYREF

  v5 = 0;
  lpMem = 0;
  if ( (xmmword_18001F260 & 4) != 0 )
  {
    WPP_SF_dqq(1026, 0x13u, (ULONGLONG)WPP_c9cb64bf9be638328d158dcace113d85_Traceguids, a1, a2, a3);
    v5 = (LPVOID *)lpMem;
  }
  if ( !a2 || !a3 )
  {
    v7 = 87;
    goto LABEL_14;
  }
  AcquireSRWLockExclusive(&g_rwZtSettingsLock);
  updated = ZtRegReadClientCerts(a2, a3, &lpMem);
  v7 = updated;
  if ( !updated )
  {
    updated = ZtUpdateClientCertsGlobal(a1, lpMem, 0);
    v7 = updated;
    if ( !updated || (xmmword_18001F260 & 4) == 0 )
      goto LABEL_13;
    v9 = 21;
    goto LABEL_12;
  }
  if ( (xmmword_18001F260 & 4) != 0 )
  {
    v9 = 20;
LABEL_12:
    WPP_SF_d(1026, v9, (ULONGLONG)WPP_c9cb64bf9be638328d158dcace113d85_Traceguids, updated);
  }
LABEL_13:
  ReleaseSRWLockExclusive(&g_rwZtSettingsLock);
  v5 = (LPVOID *)lpMem;
LABEL_14:
  if ( g_fVelocityZtdnsApiRefactor )
    ZtFreeClientCertConfig(v5);
  else
    DnsFreeZtClientCertConfig(v5);
  lpMem = 0;
  if ( (xmmword_18001F260 & 4) != 0 )
    WPP_SF_d(1026, 0x16u, (ULONGLONG)WPP_c9cb64bf9be638328d158dcace113d85_Traceguids, v7);
  return v7;
}

```

## disassembly

```asm
0x180009420  mov     rax, rsp
0x180009423  mov     [rax+8], rbx
0x180009427  mov     [rax+18h], rsi
0x18000942b  push    rdi
0x18000942c  sub     rsp, 30h
0x180009430  mov     esi, ecx
0x180009432  mov     rbx, r8
0x180009435  xor     ecx, ecx
0x180009437  mov     rdi, rdx
0x18000943a  mov     [rax+10h], rcx
0x18000943e  test    byte ptr cs:xmmword_18001F260, 4
0x180009445  jz      short loc_18000946B
0x180009447  lea     edx, [rcx+13h]
0x18000944a  mov     [rax-10h], rbx
0x18000944e  mov     ecx, 402h
0x180009453  mov     [rax-18h], rdi
0x180009457  mov     r9d, esi
0x18000945a  lea     r8, WPP_c9cb64bf9be638328d158dcace113d85_Traceguids
0x180009461  call    WPP_SF_dqq
0x180009466  mov     rcx, [rsp+38h+lpMem]
0x18000946b  test    rdi, rdi
0x18000946e  jnz     short loc_18000947A
0x180009470  mov     ebx, 57h ; 'W'
0x180009475  jmp     loc_1800094FB
0x18000947a  test    rbx, rbx
0x18000947d  jz      short loc_180009470
0x18000947f  lea     rcx, g_rwZtSettingsLock; SRWLock
0x180009486  call    cs:__imp_AcquireSRWLockExclusive
0x18000948c  lea     r8, [rsp+38h+lpMem]
0x180009491  mov     rdx, rbx
0x180009494  mov     rcx, rdi
0x180009497  call    ZtRegReadClientCerts
0x18000949c  mov     ebx, eax
0x18000949e  test    eax, eax
0x1800094a0  jnz     short loc_1800094C7
0x1800094a2  mov     rdx, [rsp+38h+lpMem]
0x1800094a7  xor     r8d, r8d
0x1800094aa  mov     ecx, esi
0x1800094ac  call    ZtUpdateClientCertsGlobal
0x1800094b1  mov     ebx, eax
0x1800094b3  test    eax, eax
0x1800094b5  jz      short loc_1800094E9
0x1800094b7  test    byte ptr cs:xmmword_18001F260, 4
0x1800094be  jz      short loc_1800094E9
0x1800094c0  mov     edx, 15h
0x1800094c5  jmp     short loc_1800094D5
0x1800094c7  test    byte ptr cs:xmmword_18001F260, 4
0x1800094ce  jz      short loc_1800094E9
0x1800094d0  mov     edx, 14h
0x1800094d5  mov     r9d, eax
0x1800094d8  lea     r8, WPP_c9cb64bf9be638328d158dcace113d85_Traceguids
0x1800094df  mov     ecx, 402h
0x1800094e4  call    WPP_SF_d
0x1800094e9  lea     rcx, g_rwZtSettingsLock; SRWLock
0x1800094f0  call    cs:__imp_ReleaseSRWLockExclusive
0x1800094f6  mov     rcx, [rsp+38h+lpMem]; lpMem
0x1800094fb  cmp     cs:g_fVelocityZtdnsApiRefactor, 0
0x180009502  jz      short loc_18000950B
0x180009504  call    ZtFreeClientCertConfig
0x180009509  jmp     short loc_180009511
0x18000950b  call    cs:__imp_DnsFreeZtClientCertConfig
0x180009511  mov     [rsp+38h+lpMem], 0
0x18000951a  test    byte ptr cs:xmmword_18001F260, 4
0x180009521  jz      short loc_18000953C
0x180009523  mov     edx, 16h
0x180009528  lea     r8, WPP_c9cb64bf9be638328d158dcace113d85_Traceguids
0x18000952f  mov     ecx, 402h
0x180009534  mov     r9d, ebx
0x180009537  call    WPP_SF_d
0x18000953c  mov     rsi, [rsp+38h+arg_10]
0x180009541  mov     eax, ebx
0x180009543  mov     rbx, [rsp+38h+arg_0]
0x180009548  add     rsp, 30h
0x18000954c  pop     rdi
0x18000954d  retn
```
