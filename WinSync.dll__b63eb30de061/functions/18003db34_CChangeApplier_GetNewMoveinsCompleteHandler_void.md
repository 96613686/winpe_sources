# CChangeApplier::GetNewMoveinsCompleteHandler(void)

- ea: `0x18003db34`
- end: `0x18003dbbc`
- name: `?GetNewMoveinsCompleteHandler@CChangeApplier@@AEAAJXZ`
- size: `136`
- prototype: `__int64 __fastcall(CChangeApplier *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180039f60`

## callees

- `0x18001a038`
- `0x18001ae20`
- `0x18003db34`

## string_xrefs

- `0x18003db5d`: `CChangeApplier::GetNewMoveinsCompleteHandler`
- `0x18003db91`: `CChangeApplier::GetNewMoveinsCompleteHandler`

## pseudocode

```c
__int64 __fastcall CChangeApplier::GetNewMoveinsCompleteHandler(CChangeApplier *this)
{
  PVOID *v1; // rcx

  v1 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
  {
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
    {
      WPP_SF_s(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        121,
        &WPP_4afb552cd4e9336475e7a5400d2892b5_Traceguids,
        "CChangeApplier::GetNewMoveinsCompleteHandler");
      v1 = (PVOID *)WPP_GLOBAL_Control;
    }
    if ( v1 != &WPP_GLOBAL_Control && (*((_BYTE *)v1 + 28) & 8) != 0 && *((_BYTE *)v1 + 25) >= 5u )
      WPP_SF_sD(
        (unsigned int)v1[2],
        122,
        (unsigned int)&WPP_4afb552cd4e9336475e7a5400d2892b5_Traceguids,
        (unsigned int)"CChangeApplier::GetNewMoveinsCompleteHandler",
        1);
  }
  return 2147500033LL;
}

```

## disassembly

```asm
0x18003db34  push    rbx
0x18003db36  sub     rsp, 30h
0x18003db3a  mov     rcx, cs:WPP_GLOBAL_Control
0x18003db41  lea     rbx, WPP_GLOBAL_Control
0x18003db48  cmp     rcx, rbx
0x18003db4b  jz      short loc_18003DBB1
0x18003db4d  test    byte ptr [rcx+1Ch], 8
0x18003db51  jz      short loc_18003DB7C
0x18003db53  cmp     byte ptr [rcx+19h], 5
0x18003db57  jb      short loc_18003DB7C
0x18003db59  mov     rcx, [rcx+10h]
0x18003db5d  lea     r9, aCchangeapplier_105; "CChangeApplier::GetNewMoveinsCompleteHa"...
0x18003db64  mov     edx, 79h ; 'y'
0x18003db69  lea     r8, WPP_4afb552cd4e9336475e7a5400d2892b5_Traceguids
0x18003db70  call    WPP_SF_s
0x18003db75  mov     rcx, cs:WPP_GLOBAL_Control
0x18003db7c  cmp     rcx, rbx
0x18003db7f  jz      short loc_18003DBB1
0x18003db81  test    byte ptr [rcx+1Ch], 8
0x18003db85  jz      short loc_18003DBB1
0x18003db87  cmp     byte ptr [rcx+19h], 5
0x18003db8b  jb      short loc_18003DBB1
0x18003db8d  mov     rcx, [rcx+10h]
0x18003db91  lea     r9, aCchangeapplier_105; "CChangeApplier::GetNewMoveinsCompleteHa"...
0x18003db98  mov     edx, 7Ah ; 'z'
0x18003db9d  mov     [rsp+38h+var_18], 80004001h
0x18003dba5  lea     r8, WPP_4afb552cd4e9336475e7a5400d2892b5_Traceguids
0x18003dbac  call    WPP_SF_sD
0x18003dbb1  mov     eax, 80004001h
0x18003dbb6  add     rsp, 30h
0x18003dbba  pop     rbx
0x18003dbbb  retn
```
