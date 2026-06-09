# SrSettings::CSrSettings::GetWifiSettingFilePath(ushort * *)

- ea: `0x18000af70`
- end: `0x18000af97`
- name: `?GetWifiSettingFilePath@CSrSettings@SrSettings@@UEAAJPEAPEAG@Z`
- size: `39`
- prototype: `__int64 __fastcall(SrSettings::CSrSettings *__hidden this, unsigned __int16 **)`
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config`

## callees

- `0x180007080`
- `0x18000af70`

## pseudocode

```c
errno_t __fastcall SrSettings::CSrSettings::GetWifiSettingFilePath(
        SrSettings::CSrSettings *this,
        unsigned __int16 **a2)
{
  __int64 v3; // rax
  _QWORD *v4; // rcx

  if ( !*((_BYTE *)this + 3945) )
    return -2147024875;
  v3 = *((_QWORD *)this + 14);
  v4 = (_QWORD *)((char *)this + 104);
  if ( *v4 == v3 )
    return -2147024846;
  else
    return CopyString((__int64)v4, (void **)a2);
}

```

## disassembly

```asm
0x18000af70  cmp     byte ptr [rcx+0F69h], 0
0x18000af77  jnz     short loc_18000AF7F
0x18000af79  mov     eax, 80070015h
0x18000af7e  retn
0x18000af7f  mov     rax, [rcx+70h]
0x18000af83  add     rcx, 68h ; 'h'
0x18000af87  cmp     [rcx], rax
0x18000af8a  jnz     short loc_18000AF92
0x18000af8c  mov     eax, 80070032h
0x18000af91  retn
0x18000af92  jmp     ?CopyString@@YAJAEAV?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@PEAPEAG@Z; CopyString(utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>> &,ushort * *)
```
