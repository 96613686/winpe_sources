# SidKeyDebugTraceError(ulong,char const *,char const *,ulong)

- ea: `0x18001a450`
- end: `0x18001a48e`
- name: `?SidKeyDebugTraceError@@YAXKPEBD0K@Z`
- size: `62`
- prototype: `void __fastcall(unsigned int, const char *, const char *, unsigned int)`
- caller_count: `114`
- callee_count: `2`
- tags: `authz_impersonation`

## callers

- `0x180002888`
- `0x180002a5c`
- `0x180002b28`
- `0x180002bf0`
- `0x180003160`
- `0x1800035a0`
- `0x180003670`
- `0x1800038c0`
- `0x18000398c`
- `0x180003b1c`
- `0x180004568`
- `0x180004624`
- `0x180004a00`
- `0x180004f9c`
- `0x180005284`
- `0x180005330`
- `0x1800054e0`
- `0x180005740`
- `0x1800058a0`
- `0x180005934`
- `0x180005a24`
- `0x180006564`
- `0x180006908`
- `0x180006dbc`
- `0x180006fb0`
- `0x180007060`
- `0x18000713c`
- `0x180007354`
- `0x180007a10`
- `0x180007b60`
- `0x180007c20`
- `0x180007d28`
- `0x180007e98`
- `0x1800080e8`
- `0x180008240`
- `0x180008570`
- `0x180008850`
- `0x18000898c`
- `0x180008afc`
- `0x180008cf0`
- `0x180008e1c`
- `0x180008eb4`
- `0x180009148`
- `0x180009408`
- `0x180009828`
- `0x180009a14`
- `0x180009ba4`
- `0x180009e04`
- `0x18000a154`
- `0x18000a26c`

## callees

- `0x18001a450`
- `0x18001a494`

## pseudocode

```c
void __fastcall SidKeyDebugTraceError(char a1, const char *a2, const char *a3, char a4)
{
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    WPP_SF_sDsd(*((_QWORD *)WPP_GLOBAL_Control + 2), (_DWORD)a2, (_DWORD)a3, (_DWORD)a2, a1, (__int64)a3, a4);
}

```

## disassembly

```asm
0x18001a450  sub     rsp, 48h
0x18001a454  mov     eax, ecx
0x18001a456  mov     rcx, cs:WPP_GLOBAL_Control
0x18001a45d  lea     r10, WPP_GLOBAL_Control
0x18001a464  cmp     rcx, r10
0x18001a467  jz      short loc_18001A489
0x18001a469  test    byte ptr [rcx+1Ch], 1
0x18001a46d  jz      short loc_18001A489
0x18001a46f  mov     rcx, [rcx+10h]
0x18001a473  mov     [rsp+48h+var_18], r9d
0x18001a478  mov     r9, rdx
0x18001a47b  mov     [rsp+48h+var_20], r8
0x18001a480  mov     [rsp+48h+var_28], eax
0x18001a484  call    WPP_SF_sDsd
0x18001a489  add     rsp, 48h
0x18001a48d  retn
```
