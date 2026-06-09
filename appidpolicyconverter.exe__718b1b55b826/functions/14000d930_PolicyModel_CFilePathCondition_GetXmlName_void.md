# PolicyModel::CFilePathCondition::GetXmlName(void)

- ea: `0x14000d930`
- end: `0x14000d995`
- name: `?GetXmlName@CFilePathCondition@PolicyModel@@MEBA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@XZ`
- size: `101`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `3`
- tags: `registry_config`

## callees

- `0x1400070e4`
- `0x1400099b4`
- `0x14000d930`

## string_xrefs

- `0x14000d973`: `FilePathCondition`

## pseudocode

```c
__int64 __fastcall PolicyModel::CFilePathCondition::GetXmlName(__int64 a1, __int64 a2)
{
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 14, WPP_a1a8c93a76de3b7ee012ad1e7d3a4a88_Traceguids);
  std::wstring::wstring(a2);
  return a2;
}

```

## disassembly

```asm
0x14000d930  mov     [rsp+arg_8], rdx
0x14000d935  push    rbx
0x14000d936  sub     rsp, 30h
0x14000d93a  mov     rbx, rdx
0x14000d93d  mov     [rsp+38h+var_18], 0
0x14000d945  lea     rax, WPP_GLOBAL_Control
0x14000d94c  mov     rcx, cs:WPP_GLOBAL_Control
0x14000d953  cmp     rcx, rax
0x14000d956  jz      short loc_14000D973
0x14000d958  test    byte ptr [rcx+1Ch], 8
0x14000d95c  jz      short loc_14000D973
0x14000d95e  mov     edx, 0Eh
0x14000d963  lea     r8, WPP_a1a8c93a76de3b7ee012ad1e7d3a4a88_Traceguids
0x14000d96a  mov     rcx, [rcx+10h]
0x14000d96e  call    WPP_SF_
0x14000d973  lea     rdx, aFilepathcondit; "FilePathCondition"
0x14000d97a  mov     rcx, rbx
0x14000d97d  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@PEBG@Z; std::wstring::wstring(ushort const *)
0x14000d982  nop
0x14000d983  mov     [rsp+38h+var_18], 1
0x14000d98b  mov     rax, rbx
0x14000d98e  add     rsp, 30h
0x14000d992  pop     rbx
0x14000d993  retn
```
