# TrySyncSetting(bond::nullable<bool,void>,ulong,ulong,ulong,ulong)

- ea: `0x18008ce50`
- end: `0x18008ced3`
- name: `?TrySyncSetting@@YA_NV?$nullable@_NX@bond@@KKKK@Z`
- size: `131`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x18008cb00`

## callees

- `0x18008ce50`
- `0x18008cedc`

## import_xrefs

- `USER32!SystemParametersInfoW` at `0x18008ce8d`
- `USER32!SystemParametersInfoW` at `0x18008cea1`
- `USER32!SystemParametersInfoW` at `0x18008ce8d`
- `USER32!SystemParametersInfoW` at `0x18008cea1`

## pseudocode

```c
char __fastcall TrySyncSetting(unsigned __int16 a1, UINT a2, UINT a3, int a4, int a5)
{
  __int16 v6; // bx
  const char *v7; // r9
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]
  int pvParam; // [rsp+30h] [rbp+8h] BYREF

  pvParam = 0;
  if ( (_BYTE)a1 )
  {
    v6 = HIBYTE(a1);
    if ( !HIBYTE(a1) )
      a4 = a5;
    pvParam = a4;
    SystemParametersInfoW(a2, 0, (PVOID)a4, 1u);
  }
  else
  {
    if ( !SystemParametersInfoW(a3, 0, &pvParam, 0) )
      wil::details::in1diag3::_Log_GetLastError(
        retaddr,
        (void *)0x47,
        (unsigned int)"pcshell\\shell\\cloudrestorelauncher\\restoredisplaysettings\\restoredisplaysettings.cpp",
        v7);
    LOBYTE(v6) = pvParam == a4;
  }
  return v6;
}

```

## disassembly

```asm
0x18008ce50  mov     [rsp+arg_8], rbx
0x18008ce55  push    rdi
0x18008ce56  sub     rsp, 20h
0x18008ce5a  mov     [rsp+28h+pvParam], 0
0x18008ce62  mov     edi, r9d
0x18008ce65  mov     eax, r8d
0x18008ce68  mov     r10d, edx
0x18008ce6b  movzx   ebx, cx
0x18008ce6e  test    cl, cl
0x18008ce70  jz      short loc_18008CE95
0x18008ce72  shr     bx, 8
0x18008ce76  mov     ecx, r10d; uiAction
0x18008ce79  test    bl, bl
0x18008ce7b  cmovz   edi, [rsp+28h+arg_20]
0x18008ce80  xor     edx, edx; uiParam
0x18008ce82  movsxd  r8, edi; pvParam
0x18008ce85  mov     [rsp+28h+pvParam], edi
0x18008ce89  lea     r9d, [rdx+1]; fWinIni
0x18008ce8d  call    cs:__imp_SystemParametersInfoW
0x18008ce93  jmp     short loc_18008CEC6
0x18008ce95  xor     r9d, r9d; fWinIni
0x18008ce98  lea     r8, [rsp+28h+pvParam]; pvParam
0x18008ce9d  xor     edx, edx; uiParam
0x18008ce9f  mov     ecx, eax; uiAction
0x18008cea1  call    cs:__imp_SystemParametersInfoW
0x18008cea7  test    eax, eax
0x18008cea9  jnz     short loc_18008CEBF
0x18008ceab  mov     rcx, [rsp+28h]; this
0x18008ceb0  lea     r8, aPcshellShellCl_30; "pcshell\\shell\\cloudrestorelauncher\\r"...
0x18008ceb7  lea     edx, [rax+47h]; void *
0x18008ceba  call    ?_Log_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Log_GetLastError(void *,uint,char const *)
0x18008cebf  cmp     [rsp+28h+pvParam], edi
0x18008cec3  setz    bl
0x18008cec6  mov     al, bl
0x18008cec8  mov     rbx, [rsp+28h+arg_8]
0x18008cecd  add     rsp, 20h
0x18008ced1  pop     rdi
0x18008ced2  retn
```
