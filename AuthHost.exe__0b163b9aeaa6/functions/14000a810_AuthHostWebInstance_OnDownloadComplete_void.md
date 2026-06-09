# AuthHostWebInstance::OnDownloadComplete(void)

- ea: `0x14000a810`
- end: `0x14000a84f`
- name: `?OnDownloadComplete@AuthHostWebInstance@@UEAAJXZ`
- size: `63`
- prototype: `__int64 __fastcall(AuthHostWebInstance *__hidden this)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x140002c70`
- `0x14000a810`

## pseudocode

```c
__int64 __fastcall AuthHostWebInstance::OnDownloadComplete(AuthHostWebInstance *this)
{
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 65) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 7), 20, &WPP_eb10dd10cfca36d0d06c224971275cc2_Traceguids);
  }
  return 0;
}

```

## disassembly

```asm
0x14000a810  sub     rsp, 28h
0x14000a814  mov     rcx, cs:WPP_GLOBAL_Control
0x14000a81b  lea     rax, WPP_GLOBAL_Control
0x14000a822  cmp     rcx, rax
0x14000a825  jz      short loc_14000A848
0x14000a827  test    byte ptr [rcx+44h], 4
0x14000a82b  jz      short loc_14000A848
0x14000a82d  cmp     byte ptr [rcx+41h], 5
0x14000a831  jb      short loc_14000A848
0x14000a833  mov     rcx, [rcx+38h]
0x14000a837  lea     r8, WPP_eb10dd10cfca36d0d06c224971275cc2_Traceguids
0x14000a83e  mov     edx, 14h
0x14000a843  call    WPP_SF_
0x14000a848  xor     eax, eax
0x14000a84a  add     rsp, 28h
0x14000a84e  retn
```
