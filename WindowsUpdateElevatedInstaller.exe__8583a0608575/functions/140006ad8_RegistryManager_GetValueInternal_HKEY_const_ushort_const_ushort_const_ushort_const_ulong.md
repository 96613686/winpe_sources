# RegistryManager::GetValueInternal(HKEY__ * const,ushort const *,ushort const *,ushort const *,ulong &)

- ea: `0x140006ad8`
- end: `0x140006b82`
- name: `?GetValueInternal@RegistryManager@@CAJQEAUHKEY__@@PEBG11AEAK@Z`
- size: `170`
- prototype: `LSTATUS __fastcall(HKEY, char *, const unsigned __int16 *, const unsigned __int16 *, unsigned __int8 *)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x140006038`

## callees

- `0x1400048e4`
- `0x140006ad8`
- `0x140006b88`

## string_xrefs

- `0x140006af5`: `onecore\enduser\windowsupdate\muse\orchestrator\common\lib\usocommon\registrymanager.cpp`
- `0x140006b5d`: `onecore\enduser\windowsupdate\muse\orchestrator\common\lib\usocommon\registrymanager.cpp`

## pseudocode

```c
LSTATUS __fastcall RegistryManager::GetValueInternal(
        HKEY a1,
        char *a2,
        const unsigned __int16 *a3,
        const unsigned __int16 *a4,
        unsigned __int8 *a5)
{
  __int64 v5; // rdx
  LSTATUS result; // eax
  int v7; // [rsp+20h] [rbp-28h]
  int v8; // [rsp+20h] [rbp-28h]
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]
  HKEY v10; // [rsp+50h] [rbp+8h] BYREF
  const unsigned __int16 *v11; // [rsp+60h] [rbp+18h] BYREF

  v11 = a3;
  v10 = a1;
  if ( !a2 )
  {
    v5 = 672;
LABEL_3:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v5,
      (unsigned int)"onecore\\enduser\\windowsupdate\\muse\\orchestrator\\common\\lib\\usocommon\\registrymanager.cpp",
      (const char *)0x80070057LL,
      v7);
    return -2147024809;
  }
  if ( !a4 )
  {
    v5 = 673;
    goto LABEL_3;
  }
  LODWORD(v10) = 4;
  LODWORD(v11) = 0;
  result = RegistryManager::GetValueInternal(a1, a2, a3, a4, (unsigned int *)&v11, a5, (unsigned int *)&v10);
  if ( result >= 0 )
  {
    if ( (_DWORD)v11 == 4 )
    {
      return 0;
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x2AE,
        (unsigned int)"onecore\\enduser\\windowsupdate\\muse\\orchestrator\\common\\lib\\usocommon\\registrymanager.cpp",
        (const char *)0x8024A215LL,
        v8);
      return -2145082859;
    }
  }
  return result;
}

```

## disassembly

```asm
0x140006ad8  mov     [rsp+arg_10], r8
0x140006add  mov     [rsp+arg_0], rcx
0x140006ae2  sub     rsp, 48h
0x140006ae6  test    rdx, rdx
0x140006ae9  jnz     short loc_140006B0E
0x140006aeb  mov     edx, 2A0h; void *
0x140006af0  mov     rcx, [rsp+48h]; this
0x140006af5  lea     r8, aOnecoreEnduser; "onecore\\enduser\\windowsupdate\\muse\\"...
0x140006afc  mov     r9d, 80070057h; char *
0x140006b02  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140006b07  mov     eax, 80070057h
0x140006b0c  jmp     short loc_140006B7D
0x140006b0e  test    r9, r9
0x140006b11  jnz     short loc_140006B1A
0x140006b13  mov     edx, 2A1h; unsigned __int16 *
0x140006b18  jmp     short loc_140006AF0
0x140006b1a  lea     rax, [rsp+48h+arg_0]
0x140006b1f  mov     dword ptr [rsp+48h+arg_0], 4
0x140006b27  mov     [rsp+48h+var_18], rax; unsigned int *
0x140006b2c  mov     rax, [rsp+48h+arg_20]
0x140006b31  mov     [rsp+48h+var_20], rax; unsigned __int8 *
0x140006b36  lea     rax, [rsp+48h+arg_10]
0x140006b3b  mov     [rsp+48h+var_28], rax; int
0x140006b40  mov     dword ptr [rsp+48h+arg_10], 0
0x140006b48  call    ?GetValueInternal@RegistryManager@@CAJQEAUHKEY__@@PEBG11AEAKPEAE2@Z; RegistryManager::GetValueInternal(HKEY__ * const,ushort const *,ushort const *,ushort const *,ulong &,uchar *,ulong &)
0x140006b4d  test    eax, eax
0x140006b4f  js      short loc_140006B7D
0x140006b51  cmp     dword ptr [rsp+48h+arg_10], 4
0x140006b56  jz      short loc_140006B7B
0x140006b58  mov     rcx, [rsp+48h]; this
0x140006b5d  lea     r8, aOnecoreEnduser; "onecore\\enduser\\windowsupdate\\muse\\"...
0x140006b64  mov     r9d, 8024A215h; char *
0x140006b6a  mov     edx, 2AEh; void *
0x140006b6f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140006b74  mov     eax, 8024A215h
0x140006b79  jmp     short loc_140006B7D
0x140006b7b  xor     eax, eax
0x140006b7d  add     rsp, 48h
0x140006b81  retn
```
