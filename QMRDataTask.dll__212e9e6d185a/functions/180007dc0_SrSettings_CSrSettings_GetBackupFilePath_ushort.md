# SrSettings::CSrSettings::GetBackupFilePath(ushort * *)

- ea: `0x180007dc0`
- end: `0x180007de7`
- name: `?GetBackupFilePath@CSrSettings@SrSettings@@UEAAJPEAPEAG@Z`
- size: `39`
- prototype: `__int64 __fastcall(SrSettings::CSrSettings *__hidden this, unsigned __int16 **)`
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config`

## callees

- `0x180007080`
- `0x180007dc0`

## pseudocode

```c
errno_t __fastcall SrSettings::CSrSettings::GetBackupFilePath(SrSettings::CSrSettings *this, unsigned __int16 **a2)
{
  __int64 v3; // rax
  _QWORD *v4; // rcx

  if ( !*((_BYTE *)this + 3945) )
    return -2147024875;
  v3 = *((_QWORD *)this + 10);
  v4 = (_QWORD *)((char *)this + 72);
  if ( *v4 == v3 )
    return -2147024846;
  else
    return CopyString((__int64)v4, (void **)a2);
}

```

## disassembly

```asm
0x180007dc0  cmp     byte ptr [rcx+0F69h], 0
0x180007dc7  jnz     short loc_180007DCF
0x180007dc9  mov     eax, 80070015h
0x180007dce  retn
0x180007dcf  mov     rax, [rcx+50h]
0x180007dd3  add     rcx, 48h ; 'H'
0x180007dd7  cmp     [rcx], rax
0x180007dda  jnz     short loc_180007DE2
0x180007ddc  mov     eax, 80070032h
0x180007de1  retn
0x180007de2  jmp     ?CopyString@@YAJAEAV?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@PEAPEAG@Z; CopyString(utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>> &,ushort * *)
```
