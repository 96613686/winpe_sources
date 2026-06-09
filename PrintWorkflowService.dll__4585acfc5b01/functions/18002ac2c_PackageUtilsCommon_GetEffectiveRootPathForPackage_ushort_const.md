# PackageUtilsCommon::GetEffectiveRootPathForPackage(ushort const *)

- ea: `0x18002ac2c`
- end: `0x18002adb9`
- name: `?GetEffectiveRootPathForPackage@PackageUtilsCommon@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEBG@Z`
- size: `397`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `2`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x18002b574`
- `0x180033c50`

## callees

- `0x18000495c`
- `0x180007424`
- `0x180008698`
- `0x1800127a4`
- `0x1800127c4`
- `0x180028710`
- `0x180029b7c`
- `0x18002ac2c`
- `0x18002c870`

## import_xrefs

- `api-ms-win-appmodel-runtime-l1-1-3!GetStagedPackagePathByFullName2` at `0x18002acb2`
- `api-ms-win-appmodel-runtime-l1-1-3!GetStagedPackagePathByFullName2` at `0x18002ad55`
- `api-ms-win-appmodel-runtime-l1-1-3!GetStagedPackagePathByFullName2` at `0x18002acb2`
- `api-ms-win-appmodel-runtime-l1-1-3!GetStagedPackagePathByFullName2` at `0x18002ad55`

## string_xrefs

- `0x18002ad92`: `onecoreuap\printscan\print\workflow\inc\PackageUtilsCommon.h`
- `0x18002ada4`: `onecoreuap\printscan\print\workflow\inc\PackageUtilsCommon.h`

## pseudocode

```c
__int64 __fastcall PackageUtilsCommon::GetEffectiveRootPathForPackage(__int64 a1, __int64 a2)
{
  int StagedPackagePathByFullName2; // eax
  __int64 v5; // r8
  bool v6; // cl
  unsigned __int64 v7; // r9
  unsigned __int64 v8; // rcx
  char *v9; // rax
  size_t v10; // rbx
  unsigned int v11; // eax
  unsigned int v13; // [rsp+20h] [rbp-20h]
  void *v14[2]; // [rsp+28h] [rbp-18h] BYREF
  char *v15; // [rsp+38h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+18h]
  unsigned int v17; // [rsp+70h] [rbp+30h] BYREF
  __int64 v18; // [rsp+78h] [rbp+38h] BYREF

  v14[0] = (void *)std::_Allocate<16,std::_Default_allocate_traits>(520);
  v15 = (char *)v14[0] + 520;
  memset_0(v14[0], 0, 0x208u);
  v14[1] = (char *)v14[0] + 520;
  v18 = 0;
  std::_Tidy_guard<std::vector<unsigned short>>::~_Tidy_guard<std::vector<unsigned short>>(&v18);
  v17 = 260;
  StagedPackagePathByFullName2 = GetStagedPackagePathByFullName2(a2, 2, &v17);
  v6 = StagedPackagePathByFullName2 != 122 && StagedPackagePathByFullName2;
  if ( StagedPackagePathByFullName2 > 0 )
    v7 = (unsigned __int16)StagedPackagePathByFullName2 | 0x80070000;
  else
    v7 = (unsigned int)StagedPackagePathByFullName2;
  if ( v6 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x23,
      (unsigned int)"onecoreuap\\printscan\\print\\workflow\\inc\\PackageUtilsCommon.h",
      (const char *)v7,
      v13);
  if ( StagedPackagePathByFullName2 == 122 )
  {
    v8 = ((char *)v14[1] - (char *)v14[0]) >> 1;
    if ( v17 >= v8 )
    {
      if ( v17 <= v8 )
        goto LABEL_17;
      if ( v17 > (unsigned __int64)((v15 - (char *)v14[0]) >> 1) )
      {
        std::vector<unsigned short>::_Resize_reallocate<std::_Value_init_tag>(v14, v17, v5, v7);
        goto LABEL_17;
      }
      v10 = 2 * (v17 - v8);
      memset_0(v14[1], 0, v10);
      v9 = (char *)v14[1] + v10;
    }
    else
    {
      v9 = (char *)v14[0] + 2 * v17;
    }
    v14[1] = v9;
LABEL_17:
    v11 = GetStagedPackagePathByFullName2(a2, 2, &v17);
    if ( v11 )
      wil::details::in1diag3::Throw_Win32(
        retaddr,
        (void *)0x27,
        (unsigned int)"onecoreuap\\printscan\\print\\workflow\\inc\\PackageUtilsCommon.h",
        (const char *)v11,
        v13);
  }
  std::wstring::wstring(a1, v14[0]);
  std::vector<unsigned short>::_Tidy(v14);
  return a1;
}

```

## disassembly

```asm
0x18002ac2c  mov     [rsp-18h+arg_0], rbx
0x18002ac31  mov     [rsp-18h+arg_8], rsi
0x18002ac36  push    rbp
0x18002ac37  push    rdi
0x18002ac38  push    r14
0x18002ac3a  mov     rbp, rsp
0x18002ac3d  sub     rsp, 40h
0x18002ac41  mov     r14, rdx
0x18002ac44  mov     rsi, rcx
0x18002ac47  xorps   xmm0, xmm0
0x18002ac4a  movdqu  xmmword ptr [rbp+var_18], xmm0
0x18002ac4f  mov     [rbp+var_8], 0
0x18002ac57  mov     edi, 208h
0x18002ac5c  mov     ecx, edi
0x18002ac5e  call    ??$_Allocate@$0BA@U_Default_allocate_traits@std@@@std@@YAPEAX_K@Z; std::_Allocate<16,std::_Default_allocate_traits>(unsigned __int64)
0x18002ac63  mov     [rbp+var_18], rax
0x18002ac67  lea     rbx, [rax+208h]
0x18002ac6e  mov     [rbp+var_8], rbx
0x18002ac72  mov     r8d, edi; Size
0x18002ac75  xor     edx, edx; Val
0x18002ac77  mov     rcx, rax; void *
0x18002ac7a  call    memset_0
0x18002ac7f  mov     [rbp+var_18+8], rbx
0x18002ac83  mov     [rbp+arg_18], 0
0x18002ac8b  lea     rcx, [rbp+arg_18]
0x18002ac8f  call    ??1?$_Tidy_guard@V?$vector@GV?$allocator@G@std@@@std@@@std@@QEAA@XZ; std::_Tidy_guard<std::vector<ushort>>::~_Tidy_guard<std::vector<ushort>>(void)
0x18002ac94  nop
0x18002ac95  mov     rax, [rbp+var_18+8]
0x18002ac99  mov     r9, [rbp+var_18]
0x18002ac9d  sub     rax, r9
0x18002aca0  sar     rax, 1
0x18002aca3  mov     [rbp+arg_10], eax
0x18002aca6  lea     r8, [rbp+arg_10]
0x18002acaa  mov     edx, 2
0x18002acaf  mov     rcx, r14
0x18002acb2  call    cs:__imp_GetStagedPackagePathByFullName2
0x18002acb8  cmp     eax, 7Ah ; 'z'
0x18002acbb  jz      short loc_18002ACC5
0x18002acbd  test    eax, eax
0x18002acbf  jz      short loc_18002ACC5
0x18002acc1  mov     cl, 1
0x18002acc3  jmp     short loc_18002ACC7
0x18002acc5  xor     cl, cl
0x18002acc7  test    eax, eax
0x18002acc9  jg      short loc_18002ACD0
0x18002accb  mov     r9d, eax
0x18002acce  jmp     short loc_18002ACDB
0x18002acd0  movzx   r9d, ax
0x18002acd4  or      r9d, 80070000h; char *
0x18002acdb  mov     r10, [rbp+18h]
0x18002acdf  test    cl, cl
0x18002ace1  jnz     loc_18002ADA4
0x18002ace7  cmp     eax, 7Ah ; 'z'
0x18002acea  jnz     short loc_18002AD63
0x18002acec  mov     ebx, [rbp+arg_10]
0x18002acef  mov     rdx, [rbp+var_18]
0x18002acf3  mov     rdi, [rbp+var_18+8]
0x18002acf7  mov     rcx, rdi
0x18002acfa  sub     rcx, rdx
0x18002acfd  sar     rcx, 1
0x18002ad00  cmp     rbx, rcx
0x18002ad03  jnb     short loc_18002AD0B
0x18002ad05  lea     rax, [rdx+rbx*2]
0x18002ad09  jmp     short loc_18002AD41
0x18002ad0b  jbe     short loc_18002AD45
0x18002ad0d  mov     rax, [rbp+var_8]
0x18002ad11  sub     rax, rdx
0x18002ad14  sar     rax, 1
0x18002ad17  cmp     rbx, rax
0x18002ad1a  jbe     short loc_18002AD2A
0x18002ad1c  mov     rdx, rbx
0x18002ad1f  lea     rcx, [rbp+var_18]
0x18002ad23  call    ??$_Resize_reallocate@U_Value_init_tag@std@@@?$vector@GV?$allocator@G@std@@@std@@AEAAX_KAEBU_Value_init_tag@1@@Z; std::vector<ushort>::_Resize_reallocate<std::_Value_init_tag>(unsigned __int64,std::_Value_init_tag const &)
0x18002ad28  jmp     short loc_18002AD45
0x18002ad2a  sub     rbx, rcx
0x18002ad2d  add     rbx, rbx
0x18002ad30  mov     r8, rbx; Size
0x18002ad33  xor     edx, edx; Val
0x18002ad35  mov     rcx, rdi; void *
0x18002ad38  call    memset_0
0x18002ad3d  lea     rax, [rbx+rdi]
0x18002ad41  mov     [rbp+var_18+8], rax
0x18002ad45  mov     r9, [rbp+var_18]
0x18002ad49  lea     r8, [rbp+arg_10]
0x18002ad4d  mov     edx, 2
0x18002ad52  mov     rcx, r14
0x18002ad55  call    cs:__imp_GetStagedPackagePathByFullName2
0x18002ad5b  mov     rcx, [rbp+18h]; this
0x18002ad5f  test    eax, eax
0x18002ad61  jnz     short loc_18002AD8F
0x18002ad63  mov     rdx, [rbp+var_18]
0x18002ad67  mov     rcx, rsi
0x18002ad6a  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18002ad6f  nop
0x18002ad70  lea     rcx, [rbp+var_18]
0x18002ad74  call    ?_Tidy@?$vector@GV?$allocator@G@std@@@std@@AEAAXXZ; std::vector<ushort>::_Tidy(void)
0x18002ad79  mov     rax, rsi
0x18002ad7c  mov     rbx, [rsp+40h+arg_0]
0x18002ad81  mov     rsi, [rsp+40h+arg_8]
0x18002ad86  add     rsp, 40h
0x18002ad8a  pop     r14
0x18002ad8c  pop     rdi
0x18002ad8d  pop     rbp
0x18002ad8e  retn
0x18002ad8f  mov     r9d, eax; char *
0x18002ad92  lea     r8, aOnecoreuapPrin_34; "onecoreuap\\printscan\\print\\workflow"...
0x18002ad99  mov     edx, 27h ; '''; void *
0x18002ad9e  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x18002ada4  lea     r8, aOnecoreuapPrin_34; "onecoreuap\\printscan\\print\\workflow"...
0x18002adab  mov     edx, 23h ; '#'; void *
0x18002adb0  mov     rcx, r10; this
0x18002adb3  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```
