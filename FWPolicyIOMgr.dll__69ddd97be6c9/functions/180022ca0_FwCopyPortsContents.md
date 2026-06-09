# FwCopyPortsContents

- ea: `0x180022ca0`
- end: `0x180022d11`
- name: `FwCopyPortsContents`
- size: `113`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x1800042c4`
- `0x180022ca0`

## import_xrefs

- `fwbase!FwArrayCopy` at `0x180022ccc`
- `fwbase!FwArrayCopy` at `0x180022ccc`

## pseudocode

```c
__int64 __fastcall FwCopyPortsContents(_WORD *a1, _WORD *a2)
{
  int v2; // ebx

  *a2 = *a1;
  v2 = FwArrayCopy(
         4,
         FwCopyPlatform,
         wistd::__function::__func<_lambda_8db0ce862824541f40dfb767113f1e28_,bool (void *,unsigned __int64,void *,unsigned __int64,unsigned int)>::destroy,
         a1 + 4,
         a2 + 4);
  if ( v2 < 0 && WPP_GLOBAL_Control != (LPCOLESTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 18, WPP_fffe468632e1369343f769dcfdbda4a1_Traceguids, (unsigned int)v2);
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x180022ca0  push    rbx
0x180022ca2  sub     rsp, 30h
0x180022ca6  movzx   eax, word ptr [rcx]
0x180022ca9  lea     r9, [rcx+8]
0x180022cad  mov     [rdx], ax
0x180022cb0  lea     r8, ?destroy@?$__func@V_lambda_8db0ce862824541f40dfb767113f1e28_@@$$A6A_NPEAX_K01I@Z@__function@wistd@@UEAAXXZ; wistd::__function::__func<_lambda_8db0ce862824541f40dfb767113f1e28_,bool (void *,unsigned __int64,void *,unsigned __int64,uint)>::destroy(void)
0x180022cb7  lea     rax, [rdx+8]
0x180022cbb  mov     ecx, 4
0x180022cc0  lea     rdx, FwCopyPlatform
0x180022cc7  mov     [rsp+38h+var_18], rax
0x180022ccc  call    cs:__imp_FwArrayCopy
0x180022cd2  mov     ebx, eax
0x180022cd4  test    eax, eax
0x180022cd6  jns     short loc_180022D09
0x180022cd8  mov     rcx, cs:WPP_GLOBAL_Control
0x180022cdf  lea     rax, WPP_GLOBAL_Control
0x180022ce6  cmp     rcx, rax
0x180022ce9  jz      short loc_180022D09
0x180022ceb  test    byte ptr [rcx+1Ch], 1
0x180022cef  jz      short loc_180022D09
0x180022cf1  mov     rcx, [rcx+10h]
0x180022cf5  lea     r8, WPP_fffe468632e1369343f769dcfdbda4a1_Traceguids
0x180022cfc  mov     edx, 12h
0x180022d01  mov     r9d, ebx
0x180022d04  call    WPP_SF_d
0x180022d09  mov     eax, ebx
0x180022d0b  add     rsp, 30h
0x180022d0f  pop     rbx
0x180022d10  retn
```
