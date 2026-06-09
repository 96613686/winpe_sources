# CheckQMGuid

- ea: `0x180037d34`
- end: `0x180037e29`
- name: `CheckQMGuid`
- size: `245`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180037fa0`
- `0x1800385b0`

## callees

- `0x18000f35c`
- `0x180037d34`
- `0x1800950b0`
- `0x1800cff88`

## import_xrefs

- `msvcrt!free` at `0x180037dd6`
- `msvcrt!free` at `0x180037dee`
- `msvcrt!free` at `0x180037e12`
- `msvcrt!free` at `0x180037dd6`
- `msvcrt!free` at `0x180037dee`
- `msvcrt!free` at `0x180037e12`
- `mqsec!IdnNameCompare` at `0x180037dc9`
- `mqsec!IdnNameCompare` at `0x180037dc9`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
char __fastcall CheckQMGuid(__int64 a1, __int64 a2, __int64 a3)
{
  int v3; // eax
  void *v4; // rbx
  __int16 v6; // [rsp+40h] [rbp-28h] BYREF
  void *Block; // [rsp+48h] [rbp-20h]
  int v8; // [rsp+70h] [rbp+8h] BYREF
  void *v9; // [rsp+78h] [rbp+10h]

  v8 = 203;
  v6 = 1;
  v3 = ADGetObjectPropertiesGuid(1, 0, a3, &CQueueMgr::m_guidQmQueue, 1, &v8, &v6);
  if ( v3 >= 0 )
  {
    v4 = Block;
    v9 = Block;
    if ( !IdnNameCompare((const wchar_t *)Block, g_szMachineName) )
    {
      free(v4);
      return 1;
    }
    if ( !dword_18013C574 )
    {
      dword_18013C574 = 1;
      EvReport(0xC00007DF, 1u, Block);
    }
    free(v4);
  }
  else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 228) & 1) != 0 )
  {
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 27),
      14,
      WPP_a89ec2e2b9d9354c8e6aafbcdab2ef85_Traceguids,
      (unsigned int)v3);
  }
  return 0;
}

```

## disassembly

```asm
0x180037d34  mov     r11, rsp
0x180037d37  mov     [r11+18h], rbx
0x180037d3b  push    rdi
0x180037d3c  sub     rsp, 60h
0x180037d40  mov     [rsp+68h+arg_0], 0CBh
0x180037d48  mov     edi, 1
0x180037d4d  mov     [rsp+68h+var_28], di
0x180037d52  lea     rax, [r11-28h]
0x180037d56  mov     [r11-38h], rax
0x180037d5a  lea     rax, [r11+8]
0x180037d5e  mov     [r11-40h], rax
0x180037d62  mov     [rsp+68h+var_48], edi
0x180037d66  lea     r9, ?m_guidQmQueue@CQueueMgr@@0U_GUID@@A; _GUID CQueueMgr::m_guidQmQueue
0x180037d6d  xor     edx, edx
0x180037d6f  mov     ecx, edi
0x180037d71  call    ?ADGetObjectPropertiesGuid@@YAJW4AD_OBJECT@@PEB_W_NPEBU_GUID@@KQEBKQEAUtagPROPVARIANT@@@Z; ADGetObjectPropertiesGuid(AD_OBJECT,wchar_t const *,bool,_GUID const *,ulong,ulong const * const,tagPROPVARIANT * const)
0x180037d76  test    eax, eax
0x180037d78  jns     short loc_180037DB5
0x180037d7a  lea     rdx, WPP_GLOBAL_Control
0x180037d81  mov     rcx, cs:WPP_GLOBAL_Control
0x180037d88  cmp     rcx, rdx
0x180037d8b  jz      loc_180037E19
0x180037d91  test    [rcx+0E4h], dil
0x180037d98  jz      short loc_180037E19
0x180037d9a  lea     edx, [rdi+0Dh]
0x180037d9d  mov     r9d, eax
0x180037da0  lea     r8, WPP_a89ec2e2b9d9354c8e6aafbcdab2ef85_Traceguids
0x180037da7  mov     rcx, [rcx+0D8h]
0x180037dae  call    WPP_SF_d
0x180037db3  jmp     short loc_180037E19
0x180037db5  mov     rbx, [rsp+68h+Block]
0x180037dba  mov     [rsp+68h+arg_8], rbx
0x180037dbf  mov     rdx, cs:?g_szMachineName@@3PEA_WEA; wchar_t * g_szMachineName
0x180037dc6  mov     rcx, rbx
0x180037dc9  call    cs:__imp_?IdnNameCompare@@YAHPEB_W0@Z; IdnNameCompare(wchar_t const *,wchar_t const *)
0x180037dcf  test    eax, eax
0x180037dd1  jnz     short loc_180037DE2
0x180037dd3  mov     rcx, rbx; Block
0x180037dd6  call    cs:__imp_free
0x180037ddc  nop
0x180037ddd  mov     al, dil
0x180037de0  jmp     short loc_180037E1B
0x180037de2  cmp     cs:dword_18013C574, 0
0x180037de9  jz      short loc_180037DF7
0x180037deb  mov     rcx, rbx; Block
0x180037dee  call    cs:__imp_free
0x180037df4  nop
0x180037df5  jmp     short loc_180037E19
0x180037df7  mov     cs:dword_18013C574, edi
0x180037dfd  mov     r8, [rsp+68h+Block]
0x180037e02  mov     edx, edi; unsigned __int16
0x180037e04  mov     ecx, 0C00007DFh; unsigned int
0x180037e09  call    ?EvReport@@YAXKGZZ; EvReport(ulong,ushort,...)
0x180037e0e  nop
0x180037e0f  mov     rcx, rbx; Block
0x180037e12  call    cs:__imp_free
0x180037e18  nop
0x180037e19  xor     al, al
0x180037e1b  mov     rbx, [rsp+68h+arg_10]
0x180037e23  add     rsp, 60h
0x180037e27  pop     rdi
0x180037e28  retn
```
