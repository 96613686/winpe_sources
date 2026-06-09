# JobHelper::DeleteContent(_SwJob)

- ea: `0x18000c588`
- end: `0x18000c72e`
- name: `?DeleteContent@JobHelper@@AEAAJU_SwJob@@@Z`
- size: `422`
- prototype: `int __high(struct _SwJob)`
- caller_count: `2`
- callee_count: `8`
- tags: `file_ops`

## callers

- `0x18000c734`
- `0x18000da10`

## callees

- `0x18000a3c0`
- `0x18000b6f4`
- `0x18000bccc`
- `0x18000bd00`
- `0x18000c588`
- `0x180011098`
- `0x180012914`
- `0x18001f420`

## import_xrefs

- `KERNEL32!DeleteFileW` at `0x18000c5d7`
- `KERNEL32!DeleteFileW` at `0x18000c66a`
- `KERNEL32!DeleteFileW` at `0x18000c5d7`
- `KERNEL32!DeleteFileW` at `0x18000c66a`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall JobHelper::DeleteContent(__int64 a1, __int64 a2)
{
  unsigned int v3; // esi
  _QWORD *v4; // rbx
  const WCHAR *v5; // rcx
  unsigned int Error; // eax
  __int64 v7; // rbx
  const WCHAR *v8; // rcx
  unsigned int v9; // eax
  LPCWSTR *v10; // r9
  __int64 i; // rax
  _BYTE v13[48]; // [rsp+40h] [rbp-E8h] BYREF
  LPCWSTR lpFileName[3]; // [rsp+70h] [rbp-B8h] BYREF
  unsigned __int64 v15; // [rsp+88h] [rbp-A0h]

  v3 = 0;
  if ( *(_QWORD *)(a2 + 208) )
  {
    v4 = (_QWORD *)(a2 + 192);
    v5 = (const WCHAR *)(*(_QWORD *)(a2 + 216) < 8u ? a2 + 192 : *v4);
    if ( !DeleteFileW(v5) )
    {
      Error = ResultFromLastError();
      v3 = Error;
      if ( WPP_GLOBAL_Control != (LPCWSTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 2) != 0 )
      {
        if ( v4[3] >= 8u )
          v4 = (_QWORD *)*v4;
        WPP_SF_Sd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          199,
          (unsigned int)&WPP_9f155fbe94773387205a22e9edb85311_Traceguids,
          (_DWORD)v4,
          Error);
      }
    }
  }
  v7 = **(_QWORD **)(a2 + 304);
  while ( v7 != *(_QWORD *)(a2 + 304) )
  {
    _FrameworkDependency::_FrameworkDependency(
      (_FrameworkDependency *)v13,
      (const struct _FrameworkDependency *)(v7 + 64));
    if ( lpFileName[2] )
    {
      v8 = (const WCHAR *)lpFileName;
      if ( v15 >= 8 )
        v8 = lpFileName[0];
      if ( !DeleteFileW(v8) )
      {
        v9 = ResultFromLastError();
        v3 = v9;
        if ( WPP_GLOBAL_Control != (LPCWSTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 2) != 0 )
        {
          v10 = lpFileName;
          if ( v15 >= 8 )
            LODWORD(v10) = lpFileName[0];
          WPP_SF_Sd(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            200,
            (unsigned int)&WPP_9f155fbe94773387205a22e9edb85311_Traceguids,
            (_DWORD)v10,
            v9);
        }
      }
    }
    _FrameworkDependency::~_FrameworkDependency((_FrameworkDependency *)v13);
    if ( !*(_BYTE *)(v7 + 25) )
    {
      if ( *(_BYTE *)(*(_QWORD *)(v7 + 16) + 25LL) )
      {
        for ( i = *(_QWORD *)(v7 + 8); !*(_BYTE *)(i + 25) && v7 == *(_QWORD *)(i + 16); i = *(_QWORD *)(i + 8) )
          v7 = i;
      }
      else
      {
        i = std::_Tree_val<std::_Tree_simple_types<std::pair<std::wstring const,_FrameworkDependency>>>::_Min();
      }
      v7 = i;
    }
  }
  _SwJob::~_SwJob((_SwJob *)a2);
  return v3;
}

```

## disassembly

```asm
0x18000c588  push    rbx
0x18000c58a  push    rsi
0x18000c58b  push    rdi
0x18000c58c  push    r14
0x18000c58e  sub     rsp, 108h
0x18000c595  mov     rax, cs:__security_cookie
0x18000c59c  xor     rax, rsp
0x18000c59f  mov     [rsp+128h+var_38], rax
0x18000c5a7  mov     rdi, rdx
0x18000c5aa  mov     [rsp+128h+var_F8], rdx
0x18000c5af  xor     esi, esi
0x18000c5b1  lea     r14, WPP_GLOBAL_Control
0x18000c5b8  cmp     [rdx+0D0h], rsi
0x18000c5bf  jz      short loc_18000C626
0x18000c5c1  lea     rbx, [rdx+0C0h]
0x18000c5c8  cmp     qword ptr [rbx+18h], 8
0x18000c5cd  jb      short loc_18000C5D4
0x18000c5cf  mov     rcx, [rbx]
0x18000c5d2  jmp     short loc_18000C5D7
0x18000c5d4  mov     rcx, rbx; lpFileName
0x18000c5d7  call    cs:__imp_DeleteFileW
0x18000c5de  nop     dword ptr [rax+rax+00h]
0x18000c5e3  test    eax, eax
0x18000c5e5  jnz     short loc_18000C626
0x18000c5e7  call    ?ResultFromLastError@@YAJXZ; ResultFromLastError(void)
0x18000c5ec  mov     esi, eax
0x18000c5ee  mov     rcx, cs:WPP_GLOBAL_Control
0x18000c5f5  cmp     rcx, r14
0x18000c5f8  jz      short loc_18000C626
0x18000c5fa  test    byte ptr [rcx+1Ch], 2
0x18000c5fe  jz      short loc_18000C626
0x18000c600  cmp     qword ptr [rbx+18h], 8
0x18000c605  jb      short loc_18000C60A
0x18000c607  mov     rbx, [rbx]
0x18000c60a  mov     edx, 0C7h
0x18000c60f  mov     [rsp+128h+var_108], eax
0x18000c613  mov     r9, rbx
0x18000c616  lea     r8, WPP_9f155fbe94773387205a22e9edb85311_Traceguids
0x18000c61d  mov     rcx, [rcx+10h]
0x18000c621  call    WPP_SF_Sd
0x18000c626  mov     rbx, [rdi+130h]
0x18000c62d  mov     rbx, [rbx]
0x18000c630  cmp     rbx, [rdi+130h]
0x18000c637  jz      loc_18000C706
0x18000c63d  lea     rdx, [rbx+40h]; struct _FrameworkDependency *
0x18000c641  lea     rcx, [rsp+128h+var_E8]; this
0x18000c646  call    ??0_FrameworkDependency@@QEAA@AEBU0@@Z; _FrameworkDependency::_FrameworkDependency(_FrameworkDependency const &)
0x18000c64b  cmp     [rsp+128h+var_A8], 0
0x18000c654  jz      short loc_18000C6C0
0x18000c656  lea     rcx, [rsp+128h+lpFileName]
0x18000c65b  cmp     [rsp+128h+var_A0], 8
0x18000c664  cmovnb  rcx, [rsp+128h+lpFileName]; lpFileName
0x18000c66a  call    cs:__imp_DeleteFileW
0x18000c671  nop     dword ptr [rax+rax+00h]
0x18000c676  test    eax, eax
0x18000c678  jnz     short loc_18000C6C0
0x18000c67a  call    ?ResultFromLastError@@YAJXZ; ResultFromLastError(void)
0x18000c67f  mov     esi, eax
0x18000c681  mov     rcx, cs:WPP_GLOBAL_Control
0x18000c688  cmp     rcx, r14
0x18000c68b  jz      short loc_18000C6C0
0x18000c68d  test    byte ptr [rcx+1Ch], 2
0x18000c691  jz      short loc_18000C6C0
0x18000c693  lea     r9, [rsp+128h+lpFileName]
0x18000c698  cmp     [rsp+128h+var_A0], 8
0x18000c6a1  cmovnb  r9, [rsp+128h+lpFileName]
0x18000c6a7  mov     edx, 0C8h
0x18000c6ac  mov     [rsp+128h+var_108], eax
0x18000c6b0  lea     r8, WPP_9f155fbe94773387205a22e9edb85311_Traceguids
0x18000c6b7  mov     rcx, [rcx+10h]
0x18000c6bb  call    WPP_SF_Sd
0x18000c6c0  lea     rcx, [rsp+128h+var_E8]; this
0x18000c6c5  call    ??1_FrameworkDependency@@QEAA@XZ; _FrameworkDependency::~_FrameworkDependency(void)
0x18000c6ca  cmp     byte ptr [rbx+19h], 0
0x18000c6ce  jnz     loc_18000C630
0x18000c6d4  mov     rcx, [rbx+10h]
0x18000c6d8  cmp     byte ptr [rcx+19h], 0
0x18000c6dc  jnz     short loc_18000C6E5
0x18000c6de  call    ?_Min@?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U_FrameworkDependency@@@std@@@std@@@std@@SAPEAU?$_Tree_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U_FrameworkDependency@@@std@@PEAX@2@PEAU32@@Z; std::_Tree_val<std::_Tree_simple_types<std::pair<std::wstring const,_FrameworkDependency>>>::_Min(std::_Tree_node<std::pair<std::wstring const,_FrameworkDependency>,void *> *)
0x18000c6e3  jmp     short loc_18000C6FE
0x18000c6e5  mov     rax, [rbx+8]
0x18000c6e9  jmp     short loc_18000C6F8
0x18000c6eb  cmp     rbx, [rax+10h]
0x18000c6ef  jnz     short loc_18000C6FE
0x18000c6f1  mov     rbx, rax
0x18000c6f4  mov     rax, [rax+8]
0x18000c6f8  cmp     byte ptr [rax+19h], 0
0x18000c6fc  jz      short loc_18000C6EB
0x18000c6fe  mov     rbx, rax
0x18000c701  jmp     loc_18000C630
0x18000c706  mov     rcx, rdi; this
0x18000c709  call    ??1_SwJob@@QEAA@XZ; _SwJob::~_SwJob(void)
0x18000c70e  mov     eax, esi
0x18000c710  mov     rcx, [rsp+128h+var_38]
0x18000c718  xor     rcx, rsp; StackCookie
0x18000c71b  call    __security_check_cookie
0x18000c720  add     rsp, 108h
0x18000c727  pop     r14
0x18000c729  pop     rdi
0x18000c72a  pop     rsi
0x18000c72b  pop     rbx
0x18000c72c  retn
```
