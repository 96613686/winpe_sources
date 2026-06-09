# RegistryManager::GetHKLMValueOrDefault<ulong>(ushort const *,ushort const *,ushort const *,ulong &,ulong)

- ea: `0x140006038`
- end: `0x140006126`
- name: `??$GetHKLMValueOrDefault@K@RegistryManager@@SAJPEBG00AEAKK@Z`
- size: `238`
- prototype: `__int64 __fastcall(HKEY, __int64, const unsigned __int16 *, unsigned int *)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x140005df4`

## callees

- `0x140006038`
- `0x1400064b8`
- `0x140006ad8`
- `0x140006cec`

## string_xrefs

- `0x14000604f`: `WindowsUpdateUXRoot`
- `0x1400060f9`: `onecore\enduser\windowsupdate\muse\orchestrator\common\lib\usocommon\registrymanager.cpp`
- `0x1400060db`: `Failed to read registry value HKLM\%ws\%ws[%ws]`

## pseudocode

```c
__int64 __fastcall RegistryManager::GetHKLMValueOrDefault<unsigned long>(
        HKEY a1,
        __int64 a2,
        const unsigned __int16 *a3,
        unsigned int *a4)
{
  int ValueInternal; // eax
  unsigned int v7; // ebx
  _BYTE *v8; // rdx
  char *v9; // r8
  __int64 i; // rcx
  char v11; // r9
  __int64 *v12; // rax
  char *v14; // [rsp+40h] [rbp-28h] BYREF
  int v15; // [rsp+54h] [rbp-14h]
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+0h]

  v14 = (char *)L"WindowsUpdateUXRoot";
  ValueInternal = RegistryManager::GetValueInternal(a1, L"WindowsUpdateUXRoot", a3, a3, a4);
  v7 = ValueInternal;
  if ( (unsigned int)(ValueInternal + 2147024894) <= 1 )
  {
    *a4 = 1;
    return 0;
  }
  if ( ValueInternal >= 0 )
    return 0;
  v8 = RegistryManager::s_defaultRedirectionMap;
  v9 = v14;
  v15 = 0;
  for ( i = *((_QWORD *)RegistryManager::s_defaultRedirectionMap + 1); !*(_BYTE *)(i + 25); i = *v12 )
  {
    if ( *(_QWORD *)(i + 32) >= (unsigned __int64)v14 )
    {
      v11 = 0;
      v8 = (_BYTE *)i;
    }
    else
    {
      v11 = 1;
    }
    v12 = (__int64 *)(i + 16);
    if ( !v11 )
      v12 = (__int64 *)i;
  }
  if ( !v8[25] && (unsigned __int64)v14 >= *((_QWORD *)v8 + 4) )
    v9 = *(char **)std::map<unsigned short const *,unsigned short const *>::operator[](i, &v14, v14);
  wil::details::in1diag3::Return_HrMsg(
    retaddr,
    (void *)0x68,
    (unsigned int)"onecore\\enduser\\windowsupdate\\muse\\orchestrator\\common\\lib\\usocommon\\registrymanager.cpp",
    (const char *)v7,
    (int)"Failed to read registry value HKLM\\%ws\\%ws[%ws]",
    v9,
    0,
    a3);
  return v7;
}

```

## disassembly

```asm
0x140006038  mov     rax, rsp
0x14000603b  mov     [rax+8], rbx
0x14000603f  mov     [rax+10h], rsi
0x140006043  push    rdi
0x140006044  sub     rsp, 60h
0x140006048  mov     rdi, r9
0x14000604b  mov     [rax-48h], r9
0x14000604f  lea     rdx, aWindowsupdateu; "WindowsUpdateUXRoot"
0x140006056  mov     r9, r8; unsigned __int16 *
0x140006059  mov     [rax-28h], rdx
0x14000605d  mov     rsi, r8
0x140006060  call    ?GetValueInternal@RegistryManager@@CAJQEAUHKEY__@@PEBG11AEAK@Z; RegistryManager::GetValueInternal(HKEY__ * const,ushort const *,ushort const *,ushort const *,ulong &)
0x140006065  mov     ebx, eax
0x140006067  lea     ecx, [rax+7FF8FFFEh]
0x14000606d  cmp     ecx, 1
0x140006070  jbe     loc_14000610E
0x140006076  xor     edi, edi
0x140006078  test    eax, eax
0x14000607a  jns     loc_140006114
0x140006080  mov     rdx, cs:?s_defaultRedirectionMap@RegistryManager@@0V?$map@PEBGPEBGU?$less@PEBG@std@@V?$allocator@U?$pair@QEBGPEBG@std@@@2@@std@@A; std::map<ushort const *,ushort const *> RegistryManager::s_defaultRedirectionMap
0x140006087  xor     eax, eax
0x140006089  mov     r8, [rsp+68h+var_28]
0x14000608e  mov     [rsp+68h+var_14], eax
0x140006092  mov     rcx, [rdx+8]
0x140006096  jmp     short loc_1400060B7
0x140006098  cmp     [rcx+20h], r8
0x14000609c  jnb     short loc_1400060A3
0x14000609e  mov     r9b, 1
0x1400060a1  jmp     short loc_1400060A9
0x1400060a3  mov     r9b, dil
0x1400060a6  mov     rdx, rcx
0x1400060a9  lea     rax, [rcx+10h]
0x1400060ad  test    r9b, r9b
0x1400060b0  cmovz   rax, rcx
0x1400060b4  mov     rcx, [rax]
0x1400060b7  cmp     [rcx+19h], dil
0x1400060bb  jz      short loc_140006098
0x1400060bd  cmp     [rdx+19h], dil
0x1400060c1  jnz     short loc_1400060D6
0x1400060c3  cmp     r8, [rdx+20h]
0x1400060c7  jb      short loc_1400060D6
0x1400060c9  lea     rdx, [rsp+68h+var_28]
0x1400060ce  call    ??A?$map@PEBGPEBGU?$less@PEBG@std@@V?$allocator@U?$pair@QEBGPEBG@std@@@2@@std@@QEAAAEAPEBGAEBQEBG@Z; std::map<ushort const *,ushort const *>::operator[](ushort const * const &)
0x1400060d3  mov     r8, [rax]
0x1400060d6  mov     rcx, [rsp+68h]; this
0x1400060db  lea     rax, aFailedToReadRe; "Failed to read registry value HKLM\\%ws"...
0x1400060e2  mov     [rsp+68h+var_30], rsi
0x1400060e7  mov     r9d, ebx; char *
0x1400060ea  mov     [rsp+68h+var_38], rdi
0x1400060ef  mov     edx, 68h ; 'h'; void *
0x1400060f4  mov     [rsp+68h+var_40], r8; char *
0x1400060f9  lea     r8, aOnecoreEnduser; "onecore\\enduser\\windowsupdate\\muse\\"...
0x140006100  mov     qword ptr [rsp+68h+var_48], rax; int
0x140006105  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x14000610a  mov     eax, ebx
0x14000610c  jmp     short loc_140006116
0x14000610e  mov     dword ptr [rdi], 1
0x140006114  xor     eax, eax
0x140006116  mov     rbx, [rsp+68h+arg_0]
0x14000611b  mov     rsi, [rsp+68h+arg_8]
0x140006120  add     rsp, 60h
0x140006124  pop     rdi
0x140006125  retn
```
