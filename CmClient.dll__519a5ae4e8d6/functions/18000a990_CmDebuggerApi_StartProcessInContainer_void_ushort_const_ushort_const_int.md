# CmDebuggerApi::StartProcessInContainer(void *,ushort const *,ushort const *,int)

- ea: `0x18000a990`
- end: `0x18000aa42`
- name: `?StartProcessInContainer@CmDebuggerApi@@UEAAJPEAXPEBG1H@Z`
- size: `178`
- prototype: `__int64 __fastcall(CmDebuggerApi *__hidden this, void *, const unsigned __int16 *, const unsigned __int16 *, int)`
- caller_count: `0`
- callee_count: `5`
- tags: `loader_planting`

## callees

- `0x1800066e4`
- `0x180007044`
- `0x180007350`
- `0x1800079d0`
- `0x18000a990`

## string_xrefs

- `0x18000a9f8`: `onecore\base\gendrv\silos\clem\client\dll\dbgapi.cpp`
- `0x18000aa26`: `onecore\base\gendrv\silos\clem\client\dll\dbgapi.cpp`

## pseudocode

```c
__int64 __fastcall CmDebuggerApi::StartProcessInContainer(
        CmDebuggerApi *this,
        __int64 a2,
        const unsigned __int16 *a3,
        const unsigned __int16 *a4,
        int a5)
{
  int v5; // eax
  unsigned int v6; // ebx
  int v8; // eax
  int v9; // [rsp+20h] [rbp-48h]
  _QWORD v10[3]; // [rsp+40h] [rbp-28h] BYREF
  int v11; // [rsp+58h] [rbp-10h]
  int v12; // [rsp+5Ch] [rbp-Ch]
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+0h]
  __int64 v14; // [rsp+80h] [rbp+18h] BYREF

  v10[1] = 0;
  v12 = 0;
  v10[0] = a3;
  v10[2] = a4;
  v11 = a5;
  v14 = 0;
  v5 = CmsCreateProcessInContainer(a2, (__int64)v10, 0, 0, 0, 0, &v14);
  v6 = v5;
  if ( v5 >= 0 )
  {
    v8 = CmsCloseProcess(&v14);
    if ( v8 < 0 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x126,
        (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\client\\dll\\dbgapi.cpp",
        (const char *)(unsigned int)v8,
        v9);
    return 0;
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x124,
      (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\client\\dll\\dbgapi.cpp",
      (const char *)(unsigned int)v5,
      v9);
    return v6;
  }
}

```

## disassembly

```asm
0x18000a990  mov     r11, rsp
0x18000a993  push    rbx
0x18000a994  sub     rsp, 60h
0x18000a998  mov     eax, [rsp+68h+arg_20]
0x18000a99f  mov     rcx, rdx
0x18000a9a2  mov     qword ptr [r11-20h], 0
0x18000a9aa  lea     rdx, [r11-28h]
0x18000a9ae  mov     [rsp+68h+var_C], 0
0x18000a9b6  mov     [r11-28h], r8
0x18000a9ba  xor     r8d, r8d
0x18000a9bd  mov     [r11-18h], r9
0x18000a9c1  xor     r9d, r9d
0x18000a9c4  mov     [rsp+68h+var_10], eax
0x18000a9c8  lea     rax, [r11+18h]
0x18000a9cc  mov     [r11-38h], rax
0x18000a9d0  mov     qword ptr [r11-40h], 0
0x18000a9d8  mov     qword ptr [r11-48h], 0
0x18000a9e0  mov     qword ptr [r11+18h], 0
0x18000a9e8  call    CmsCreateProcessInContainer
0x18000a9ed  mov     ebx, eax
0x18000a9ef  test    eax, eax
0x18000a9f1  jns     short loc_18000AA10
0x18000a9f3  mov     rcx, [rsp+68h]; this
0x18000a9f8  lea     r8, aOnecoreBaseGen_4; "onecore\\base\\gendrv\\silos\\clem\\cli"...
0x18000a9ff  mov     r9d, eax; char *
0x18000aa02  mov     edx, 124h; void *
0x18000aa07  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000aa0c  mov     eax, ebx
0x18000aa0e  jmp     short loc_18000AA3C
0x18000aa10  lea     rcx, [rsp+68h+arg_10]
0x18000aa18  call    CmsCloseProcess
0x18000aa1d  test    eax, eax
0x18000aa1f  jns     short loc_18000AA3A
0x18000aa21  mov     rcx, [rsp+68h]; this
0x18000aa26  lea     r8, aOnecoreBaseGen_4; "onecore\\base\\gendrv\\silos\\clem\\cli"...
0x18000aa2d  mov     r9d, eax; char *
0x18000aa30  mov     edx, 126h; void *
0x18000aa35  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18000aa3a  xor     eax, eax
0x18000aa3c  add     rsp, 60h
0x18000aa40  pop     rbx
0x18000aa41  retn
```
