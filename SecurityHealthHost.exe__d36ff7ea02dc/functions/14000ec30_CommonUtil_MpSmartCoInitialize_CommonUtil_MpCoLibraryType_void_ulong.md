# CommonUtil::MpSmartCoInitialize(CommonUtil::MpCoLibraryType * *,void *,ulong)

- ea: `0x14000ec30`
- end: `0x14000eca1`
- name: `?MpSmartCoInitialize@CommonUtil@@YAJPEAPEAUMpCoLibraryType@1@PEAXK@Z`
- size: `113`
- prototype: `__int64 __fastcall(CommonUtil *this, struct CommonUtil::MpCoLibraryType **, void *)`
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x140002a94`
- `0x140003188`

## callees

- `0x14000d068`
- `0x14000ec30`

## import_xrefs

- `ole32!CoInitializeEx` at `0x14000ec41`
- `ole32!CoInitializeEx` at `0x14000ec41`

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
      WPP_SF_Dd(*((_QWORD *)WPP_GLOBAL_Control + 2), 15, &WPP_8880596c7910348ee12b1ef2c152e667_Traceguids, 0, v4);
    }
    return v5;
  }
}

```

## disassembly

```asm
0x14000ec30  mov     [rsp+arg_0], rbx
0x14000ec35  push    rdi
0x14000ec36  sub     rsp, 30h
0x14000ec3a  mov     rdi, rcx
0x14000ec3d  xor     edx, edx; dwCoInit
0x14000ec3f  xor     ecx, ecx; pvReserved
0x14000ec41  call    cs:__imp_CoInitializeEx
0x14000ec47  mov     ebx, eax
0x14000ec49  test    eax, eax
0x14000ec4b  jns     short loc_14000EC8D
0x14000ec4d  cmp     eax, 80010106h
0x14000ec52  jz      short loc_14000EC89
0x14000ec54  mov     rcx, cs:WPP_GLOBAL_Control
0x14000ec5b  lea     rax, WPP_GLOBAL_Control
0x14000ec62  cmp     rcx, rax
0x14000ec65  jz      short loc_14000EC89
0x14000ec67  test    byte ptr [rcx+1Ch], 1
0x14000ec6b  jz      short loc_14000EC89
0x14000ec6d  mov     rcx, [rcx+10h]
0x14000ec71  lea     r8, WPP_8880596c7910348ee12b1ef2c152e667_Traceguids
0x14000ec78  mov     edx, 0Fh
0x14000ec7d  mov     [rsp+38h+var_18], ebx
0x14000ec81  xor     r9d, r9d
0x14000ec84  call    WPP_SF_Dd
0x14000ec89  mov     eax, ebx
0x14000ec8b  jmp     short loc_14000EC96
0x14000ec8d  mov     qword ptr [rdi], 12345678h
0x14000ec94  xor     eax, eax
0x14000ec96  mov     rbx, [rsp+38h+arg_0]
0x14000ec9b  add     rsp, 30h
0x14000ec9f  pop     rdi
0x14000eca0  retn
```
