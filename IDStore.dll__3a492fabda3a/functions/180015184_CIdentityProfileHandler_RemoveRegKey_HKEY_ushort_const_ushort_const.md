# CIdentityProfileHandler::_RemoveRegKey(HKEY__ *,ushort const *,ushort const *)

- ea: `0x180015184`
- end: `0x1800152aa`
- name: `?_RemoveRegKey@CIdentityProfileHandler@@AEAAJPEAUHKEY__@@PEBG1@Z`
- size: `294`
- prototype: `__int64 __fastcall(CIdentityProfileHandler *this, HKEY, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, loader_planting`

## callers

- `0x1800146c0`

## callees

- `0x180002030`
- `0x180003560`
- `0x18000acb0`
- `0x1800145a0`
- `0x180015184`
- `0x180015374`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegDeleteTreeW` at `0x18001524a`
- `api-ms-win-core-registry-l1-1-0!RegDeleteTreeW` at `0x18001524a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180015220`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180015220`

## string_xrefs

- `0x1800151af`: `CIdentityProfileHandler::_RemoveRegKey`

## pseudocode

```c
__int64 __fastcall CIdentityProfileHandler::_RemoveRegKey(
        CIdentityProfileHandler *this,
        HKEY a2,
        const unsigned __int16 *a3,
        const unsigned __int16 *a4)
{
  CIdentityProfileHandler *v6; // rcx
  __int64 v7; // rdx
  __int64 v8; // r8
  int v9; // edi
  LSTATUS v11; // eax
  _BYTE v12[16]; // [rsp+30h] [rbp-10h] BYREF
  HLOCAL hMem; // [rsp+60h] [rbp+20h] BYREF
  int v14; // [rsp+68h] [rbp+28h] BYREF
  int v15; // [rsp+6Ch] [rbp+2Ch]

  v15 = HIDWORD(a2);
  hMem = this;
  v14 = -2147467259;
  CLogBlock::CLogBlock((CLogBlock *)v12, "CIdentityProfileHandler::_RemoveRegKey", &v14);
  hMem = 0;
  v14 = CIdentityProfileHandler::_CreatePathKey(v6, a3, a4, &hMem);
  v9 = v14;
  if ( v14 >= 0 )
  {
    v11 = RegDeleteTreeW(HKEY_LOCAL_MACHINE, (LPCWSTR)hMem);
    v9 = v11;
    if ( !v11 )
      goto LABEL_5;
    if ( v11 == 2 )
    {
      v9 = 0;
    }
    else
    {
      if ( WPP_GLOBAL_Control != (CIdentityProfileHandler *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
      {
        WPP_SF_Sd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          25,
          (unsigned int)WPP_0955e053d70b3b28b837838791dca877_Traceguids,
          (_DWORD)hMem,
          v11);
      }
      if ( v9 > 0 )
        v9 = (unsigned __int16)v9 | 0x80070000;
    }
    v14 = v9;
  }
  else if ( WPP_GLOBAL_Control != (CIdentityProfileHandler *)&WPP_GLOBAL_Control
         && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
  {
    WPP_SF_SSd(*((_QWORD *)WPP_GLOBAL_Control + 2), 24, v8, (_DWORD)a3, (__int64)a4, v14);
LABEL_5:
    v9 = v14;
  }
  if ( hMem )
    LocalFree(hMem);
  CLogBlock::~CLogBlock((CLogBlock *)v12, v7, v8);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x180015184  mov     [rsp-18h+arg_10], rsi
0x180015189  mov     qword ptr [rsp-18h+arg_8], rdx
0x18001518e  mov     [rsp-18h+hMem], rcx
0x180015193  push    rbp
0x180015194  push    rdi
0x180015195  push    r14
0x180015197  mov     rbp, rsp
0x18001519a  sub     rsp, 40h
0x18001519e  mov     r14, r8
0x1800151a1  mov     [rbp+arg_8], 80004005h
0x1800151a8  lea     r8, [rbp+arg_8]; int *
0x1800151ac  mov     rsi, r9
0x1800151af  lea     rdx, aCidentityprofi_3; "CIdentityProfileHandler::_RemoveRegKey"
0x1800151b6  lea     rcx, [rbp+var_10]; this
0x1800151ba  call    ??0CLogBlock@@QEAA@PEBDPEAJ@Z; CLogBlock::CLogBlock(char const *,long *)
0x1800151bf  lea     r9, [rbp+hMem]; void **
0x1800151c3  mov     [rbp+hMem], 0
0x1800151cb  mov     r8, rsi; unsigned __int16 *
0x1800151ce  mov     rdx, r14; unsigned __int16 *
0x1800151d1  call    ?_CreatePathKey@CIdentityProfileHandler@@AEAAJPEBG0PEAPEAX@Z; CIdentityProfileHandler::_CreatePathKey(ushort const *,ushort const *,void * *)
0x1800151d6  mov     [rbp+arg_8], eax
0x1800151d9  mov     edi, eax
0x1800151db  test    eax, eax
0x1800151dd  jns     short loc_18001523F
0x1800151df  mov     rcx, cs:WPP_GLOBAL_Control
0x1800151e6  lea     rax, WPP_GLOBAL_Control
0x1800151ed  cmp     rcx, rax
0x1800151f0  jz      short loc_180015215
0x1800151f2  test    byte ptr [rcx+1Ch], 4
0x1800151f6  jz      short loc_180015215
0x1800151f8  mov     rcx, [rcx+10h]
0x1800151fc  mov     edx, 18h
0x180015201  mov     [rsp+40h+var_18], edi
0x180015205  mov     r9, r14
0x180015208  mov     [rsp+40h+var_20], rsi
0x18001520d  call    WPP_SF_SSd
0x180015212  mov     edi, [rbp+arg_8]
0x180015215  cmp     [rbp+hMem], 0
0x18001521a  jz      short loc_180015226
0x18001521c  mov     rcx, [rbp+hMem]; hMem
0x180015220  call    cs:__imp_LocalFree
0x180015226  lea     rcx, [rbp+var_10]; this
0x18001522a  call    ??1CLogBlock@@QEAA@XZ; CLogBlock::~CLogBlock(void)
0x18001522f  mov     rsi, [rsp+40h+arg_10]
0x180015234  mov     eax, edi
0x180015236  add     rsp, 40h
0x18001523a  pop     r14
0x18001523c  pop     rdi
0x18001523d  pop     rbp
0x18001523e  retn
0x18001523f  mov     rdx, [rbp+hMem]; lpSubKey
0x180015243  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18001524a  call    cs:__imp_RegDeleteTreeW
0x180015250  mov     edi, eax
0x180015252  test    eax, eax
0x180015254  jz      short loc_180015212
0x180015256  cmp     eax, 2
0x180015259  jz      short loc_1800152A6
0x18001525b  mov     rcx, cs:WPP_GLOBAL_Control
0x180015262  lea     rax, WPP_GLOBAL_Control
0x180015269  cmp     rcx, rax
0x18001526c  jz      short loc_180015291
0x18001526e  test    byte ptr [rcx+1Ch], 4
0x180015272  jz      short loc_180015291
0x180015274  mov     r9, [rbp+hMem]
0x180015278  lea     r8, WPP_0955e053d70b3b28b837838791dca877_Traceguids
0x18001527f  mov     rcx, [rcx+10h]
0x180015283  mov     edx, 19h
0x180015288  mov     dword ptr [rsp+40h+var_20], edi
0x18001528c  call    WPP_SF_Sd
0x180015291  test    edi, edi
0x180015293  jle     short loc_18001529E
0x180015295  movzx   edi, di
0x180015298  or      edi, 80070000h
0x18001529e  mov     [rbp+arg_8], edi
0x1800152a1  jmp     loc_180015215
0x1800152a6  xor     edi, edi
0x1800152a8  jmp     short loc_18001529E
```
