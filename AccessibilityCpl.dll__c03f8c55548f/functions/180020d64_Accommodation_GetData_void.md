# Accommodation::GetData(void *)

- ea: `0x180020d64`
- end: `0x180020df3`
- name: `?GetData@Accommodation@@QEAAXPEAX@Z`
- size: `143`
- prototype: `void(Accommodation *__hidden this, void *)`
- caller_count: `25`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180016494`
- `0x180016800`
- `0x180016b44`
- `0x180016ee4`
- `0x180017114`
- `0x180017464`
- `0x180017670`
- `0x1800178c0`
- `0x180018768`
- `0x1800187e0`
- `0x180018878`
- `0x180018a28`
- `0x180018cf0`
- `0x180018d80`
- `0x180018ea0`
- `0x180018fe8`
- `0x180019194`
- `0x1800196c8`
- `0x180019be4`
- `0x180019c5c`
- `0x180019e68`
- `0x180019fcc`
- `0x18001a13c`
- `0x18001a450`
- `0x18001a4c8`

## callees

- `0x180020d64`

## import_xrefs

- `msvcrt!_wtoi` at `0x180020d78`
- `msvcrt!_wtoi` at `0x180020d78`
- `USER32!SystemParametersInfoW` at `0x180020de2`
- `USER32!SystemParametersInfoW` at `0x180020de2`

## pseudocode

```c
void __fastcall Accommodation::GetData(const wchar_t **this, _DWORD *a2)
{
  unsigned int v4; // eax
  __int64 v5; // rcx
  char *v6; // rax
  signed __int64 v7; // r9
  int v8; // r8d
  int v9; // edx
  int v10; // edx
  int v11; // edx
  UINT v12; // edx

  v4 = _wtoi(this[3]);
  if ( v4 < 0x16 )
  {
    v5 = 32LL * v4;
    v6 = *(char **)((char *)&SystemSettings::_systemSetting + v5);
    v7 = (char *)*this - v6;
    do
    {
      v8 = *(unsigned __int16 *)&v6[v7];
      v9 = *(unsigned __int16 *)v6 - v8;
      if ( v9 )
        break;
      v6 += 2;
    }
    while ( v8 );
    if ( !v9 )
    {
      v10 = *(_DWORD *)((char *)&SystemSettings::_systemSetting + v5 + 16);
      if ( v10 && (v11 = v10 - 1) != 0 )
      {
        if ( v11 != 1 )
          return;
        *a2 = *(_DWORD *)((char *)&SystemSettings::_systemSetting + v5 + 20);
        v12 = *(_DWORD *)((char *)&SystemSettings::_systemSetting + v5 + 20);
      }
      else
      {
        v12 = 0;
      }
      SystemParametersInfoW(*(_DWORD *)((char *)&SystemSettings::_systemSetting + v5 + 8), v12, a2, 0);
    }
  }
}

```

## disassembly

```asm
0x180020d64  mov     [rsp+arg_0], rbx
0x180020d69  push    rdi
0x180020d6a  sub     rsp, 20h
0x180020d6e  mov     rbx, rcx
0x180020d71  mov     rdi, rdx
0x180020d74  mov     rcx, [rcx+18h]; String
0x180020d78  call    cs:__imp__wtoi
0x180020d7e  cmp     eax, 16h
0x180020d81  jnb     short loc_180020DE8
0x180020d83  mov     r9, [rbx]
0x180020d86  lea     r10, ?_systemSetting@SystemSettings@@0PAUSystemSetting@@A; SystemSetting near * SystemSettings::_systemSetting
0x180020d8d  mov     ecx, eax
0x180020d8f  shl     rcx, 5
0x180020d93  mov     rax, [rcx+r10]
0x180020d97  sub     r9, rax
0x180020d9a  movzx   edx, word ptr [rax]
0x180020d9d  movzx   r8d, word ptr [rax+r9]
0x180020da2  sub     edx, r8d
0x180020da5  jnz     short loc_180020DB0
0x180020da7  add     rax, 2
0x180020dab  test    r8d, r8d
0x180020dae  jnz     short loc_180020D9A
0x180020db0  test    edx, edx
0x180020db2  jnz     short loc_180020DE8
0x180020db4  mov     edx, [rcx+r10+10h]
0x180020db9  test    edx, edx
0x180020dbb  jz      short loc_180020DD5
0x180020dbd  sub     edx, 1
0x180020dc0  jz      short loc_180020DD5
0x180020dc2  cmp     edx, 1
0x180020dc5  jnz     short loc_180020DE8
0x180020dc7  mov     eax, [rcx+r10+14h]
0x180020dcc  mov     [rdi], eax
0x180020dce  mov     edx, [rcx+r10+14h]
0x180020dd3  jmp     short loc_180020DD7
0x180020dd5  xor     edx, edx; uiParam
0x180020dd7  mov     ecx, [rcx+r10+8]; uiAction
0x180020ddc  xor     r9d, r9d; fWinIni
0x180020ddf  mov     r8, rdi; pvParam
0x180020de2  call    cs:__imp_SystemParametersInfoW
0x180020de8  mov     rbx, [rsp+28h+arg_0]
0x180020ded  add     rsp, 20h
0x180020df1  pop     rdi
0x180020df2  retn
```
