# CAdapter::SetPersistentSoftwareRadioOffState(uchar)

- ea: `0x14007aa9c`
- end: `0x14007ab71`
- name: `?SetPersistentSoftwareRadioOffState@CAdapter@@QEAAHE@Z`
- size: `213`
- prototype: `__int64 __fastcall(CAdapter *__hidden this, unsigned __int8)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x14004a300`

## callees

- `0x14007aa9c`
- `0x14007c428`

## import_xrefs

- `NDIS!NdisCloseConfiguration` at `0x14007ab52`
- `NDIS!NdisCloseConfiguration` at `0x14007ab52`

## pseudocode

```c
__int64 __fastcall CAdapter::SetPersistentSoftwareRadioOffState(CAdapter *this, unsigned __int8 a2)
{
  unsigned int v2; // r8d
  unsigned int v3; // eax
  int v4; // edi
  unsigned int v5; // ebx
  unsigned int v6; // r11d
  unsigned int v7; // r9d
  unsigned int v8; // r10d
  int v9; // edx
  unsigned int v10; // eax
  signed int v11; // ecx
  __int64 v12; // rcx
  __int128 v13; // xmm1
  __int64 v14; // xmm0_8
  void *m_MiniportAdapterHandle; // [rsp+20h] [rbp-48h] BYREF
  NDIS_HANDLE ConfigurationHandle; // [rsp+28h] [rbp-40h]
  __int128 v18; // [rsp+30h] [rbp-38h] BYREF
  __int128 v19; // [rsp+40h] [rbp-28h]
  __int64 v20; // [rsp+50h] [rbp-18h]

  v2 = 0;
  m_MiniportAdapterHandle = this->m_MiniportAdapterHandle;
  v3 = 0;
  v4 = a2;
  v5 = -1073741823;
  ConfigurationHandle = 0;
  do
  {
    v6 = v3;
    v7 = v2;
    v8 = v2;
    v9 = *((_DWORD *)&g_AdapterRegTable + 10 * (int)v2 + 6);
    if ( v9 == 116 )
      break;
    v3 = ++v2;
  }
  while ( v2 < 0x2B );
  v10 = v8 + 1;
  v11 = v7 + 1;
  if ( v9 == 116 )
  {
    v10 = v6;
    v11 = v7;
  }
  if ( v10 < 0x2B )
  {
    v12 = 5LL * v11;
    v13 = *(_OWORD *)(&g_AdapterRegTable + v12 + 2);
    v18 = *(_OWORD *)(&g_AdapterRegTable + v12);
    v14 = (__int64)*(&g_AdapterRegTable + v12 + 4);
    v19 = v13;
    HIDWORD(v19) = v4;
    v20 = v14;
    v5 = CRegistryHelper::WriteAdapterRegistryEntry(
           (CRegistryHelper *)&m_MiniportAdapterHandle,
           (struct _WFC_REG_ENTRY *)&v18);
    if ( ConfigurationHandle )
      NdisCloseConfiguration(ConfigurationHandle);
  }
  return v5;
}

```

## disassembly

```asm
0x14007aa9c  mov     r11, rsp
0x14007aa9f  mov     [r11+8], rbx
0x14007aaa3  mov     [r11+10h], rsi
0x14007aaa7  push    rdi
0x14007aaa8  sub     rsp, 60h
0x14007aaac  mov     rax, [rcx+58h]
0x14007aab0  lea     rsi, ?g_AdapterRegTable@@3PAU_WFC_REG_ENTRY@@A; " \""
0x14007aab7  xor     r8d, r8d
0x14007aaba  mov     [r11-48h], rax
0x14007aabe  xor     eax, eax
0x14007aac0  movzx   edi, dl
0x14007aac3  mov     ebx, 0C0000001h
0x14007aac8  mov     qword ptr [r11-40h], 0
0x14007aad0  mov     r11d, eax
0x14007aad3  mov     r9d, r8d
0x14007aad6  movsxd  rax, r8d
0x14007aad9  mov     r10d, r8d
0x14007aadc  lea     rcx, [rax+rax*4]
0x14007aae0  mov     edx, [rsi+rcx*8+18h]
0x14007aae4  cmp     edx, 74h ; 't'
0x14007aae7  jz      short loc_14007AAF5
0x14007aae9  inc     r8d
0x14007aaec  mov     eax, r8d
0x14007aaef  cmp     r8d, 2Bh ; '+'
0x14007aaf3  jb      short loc_14007AAD0
0x14007aaf5  cmp     edx, 74h ; 't'
0x14007aaf8  lea     eax, [r10+1]
0x14007aafc  lea     ecx, [r9+1]
0x14007ab00  cmovz   eax, r11d
0x14007ab04  cmovz   ecx, r9d
0x14007ab08  cmp     eax, 2Bh ; '+'
0x14007ab0b  jnb     short loc_14007AB5E
0x14007ab0d  movsxd  rax, ecx
0x14007ab10  lea     rdx, [rsp+68h+var_38]; struct _WFC_REG_ENTRY *
0x14007ab15  lea     rcx, [rax+rax*4]
0x14007ab19  movups  xmm0, xmmword ptr [rsi+rcx*8]
0x14007ab1d  movups  xmm1, xmmword ptr [rsi+rcx*8+10h]
0x14007ab22  movups  [rsp+68h+var_38], xmm0
0x14007ab27  movsd   xmm0, qword ptr [rsi+rcx*8+20h]
0x14007ab2d  lea     rcx, [rsp+68h+var_48]; this
0x14007ab32  movups  [rsp+68h+var_28], xmm1
0x14007ab37  mov     dword ptr [rsp+68h+var_28+0Ch], edi
0x14007ab3b  movsd   [rsp+68h+var_18], xmm0
0x14007ab41  call    ?WriteAdapterRegistryEntry@CRegistryHelper@@QEAAHPEAU_WFC_REG_ENTRY@@@Z; CRegistryHelper::WriteAdapterRegistryEntry(_WFC_REG_ENTRY *)
0x14007ab46  mov     rcx, [rsp+68h+ConfigurationHandle]; ConfigurationHandle
0x14007ab4b  mov     ebx, eax
0x14007ab4d  test    rcx, rcx
0x14007ab50  jz      short loc_14007AB5E
0x14007ab52  call    cs:__imp_NdisCloseConfiguration
0x14007ab59  nop     dword ptr [rax+rax+00h]
0x14007ab5e  mov     rsi, [rsp+68h+arg_8]
0x14007ab63  mov     eax, ebx
0x14007ab65  mov     rbx, [rsp+68h+arg_0]
0x14007ab6a  add     rsp, 60h
0x14007ab6e  pop     rdi
0x14007ab6f  retn
```
