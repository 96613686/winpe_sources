# CommonUtil::MpSmartCoInitialize(CommonUtil::MpCoLibraryType * *,void *,ulong)

- ea: `0x180008d68`
- end: `0x180008dd9`
- name: `?MpSmartCoInitialize@CommonUtil@@YAJPEAPEAUMpCoLibraryType@1@PEAXK@Z`
- size: `113`
- prototype: `__int64 __fastcall(CommonUtil *__hidden this, struct CommonUtil::MpCoLibraryType **, void *, unsigned int)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180008bd4`

## callees

- `0x18000766c`
- `0x180008d68`

## import_xrefs

- `ole32!CoInitializeEx` at `0x180008d79`
- `ole32!CoInitializeEx` at `0x180008d79`

## pseudocode

```c
__int64 __fastcall CommonUtil::MpSmartCoInitialize(CommonUtil *this, struct CommonUtil::MpCoLibraryType **a2, void *a3)
{
  HRESULT v4; // eax
  unsigned int v5; // ebx

  v4 = CoInitializeEx(0, 0);
  v5 = v4;
  if ( v4 >= 0 )
  {
    *(_QWORD *)this = 305419896;
    return 0;
  }
  else
  {
    if ( v4 != -2147417850
      && WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      WPP_SF_Dd(*((_QWORD *)WPP_GLOBAL_Control + 2), 15, &WPP_1c756af73aa03d742fb0eb712210c2f8_Traceguids, 0, v4);
    }
    return v5;
  }
}

```

## disassembly

```asm
0x180008d68  mov     [rsp+arg_0], rbx
0x180008d6d  push    rdi
0x180008d6e  sub     rsp, 30h
0x180008d72  mov     rdi, rcx
0x180008d75  xor     edx, edx; dwCoInit
0x180008d77  xor     ecx, ecx; pvReserved
0x180008d79  call    cs:__imp_CoInitializeEx
0x180008d7f  mov     ebx, eax
0x180008d81  test    eax, eax
0x180008d83  jns     short loc_180008DC5
0x180008d85  cmp     eax, 80010106h
0x180008d8a  jz      short loc_180008DC1
0x180008d8c  mov     rcx, cs:WPP_GLOBAL_Control
0x180008d93  lea     rax, WPP_GLOBAL_Control
0x180008d9a  cmp     rcx, rax
0x180008d9d  jz      short loc_180008DC1
0x180008d9f  test    byte ptr [rcx+1Ch], 1
0x180008da3  jz      short loc_180008DC1
0x180008da5  mov     rcx, [rcx+10h]
0x180008da9  lea     r8, WPP_1c756af73aa03d742fb0eb712210c2f8_Traceguids
0x180008db0  mov     edx, 0Fh
0x180008db5  mov     [rsp+38h+var_18], ebx
0x180008db9  xor     r9d, r9d
0x180008dbc  call    WPP_SF_Dd
0x180008dc1  mov     eax, ebx
0x180008dc3  jmp     short loc_180008DCE
0x180008dc5  mov     qword ptr [rdi], 12345678h
0x180008dcc  xor     eax, eax
0x180008dce  mov     rbx, [rsp+38h+arg_0]
0x180008dd3  add     rsp, 30h
0x180008dd7  pop     rdi
0x180008dd8  retn
```
