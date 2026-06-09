# PolicyModel::CSddlCompiler::EncodeExpression(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,bool)

- ea: `0x14000c308`
- end: `0x14000c44b`
- name: `?EncodeExpression@CSddlCompiler@PolicyModel@@SA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBV34@_N@Z`
- size: `323`
- prototype: `__int64 __fastcall(__int64, _QWORD *, unsigned __int8)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callers

- `0x14000cf50`

## callees

- `0x140001d1c`
- `0x1400070e4`
- `0x140007428`
- `0x1400099b4`
- `0x14000bcb4`
- `0x14000c308`
- `0x140013b10`

## import_xrefs

- `srpapi!AppIDFreeAttributeString` at `0x14000c414`
- `srpapi!AppIDFreeAttributeString` at `0x14000c414`
- `srpapi!AppIDEncodeAttributeString` at `0x14000c38c`
- `srpapi!AppIDEncodeAttributeString` at `0x14000c38c`

## pseudocode

```c
__int64 __fastcall PolicyModel::CSddlCompiler::EncodeExpression(__int64 a1, _QWORD *a2, unsigned __int8 a3)
{
  unsigned int v3; // esi
  int v6; // eax
  signed int v7; // ebx
  __int64 v8; // rbx
  _QWORD v10[3]; // [rsp+28h] [rbp-80h] BYREF
  _BYTE pExceptionObject[64]; // [rsp+40h] [rbp-68h] BYREF

  v3 = a3;
  v10[2] = a1;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 17, WPP_78e66d69943b3de38e95864888fb0f14_Traceguids);
  v10[0] = 0;
  if ( a2[3] >= 8u )
    a2 = (_QWORD *)*a2;
  v6 = AppIDEncodeAttributeString(a2, v3, v10);
  v7 = v6;
  if ( v6 > 0 )
    v7 = (unsigned __int16)v6 | 0x80070000;
  if ( v7 < 0 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        18,
        WPP_78e66d69943b3de38e95864888fb0f14_Traceguids,
        (unsigned int)v7);
    sddl_compiler_exception::sddl_compiler_exception((sddl_compiler_exception *)pExceptionObject, v7);
    throw (sddl_compiler_exception *)pExceptionObject;
  }
  v8 = v10[0];
  v10[1] = v10[0];
  std::wstring::wstring(a1);
  if ( v8 )
    AppIDFreeAttributeString(v8);
  return a1;
}

```

## disassembly

```asm
0x14000c308  mov     [rsp+arg_18], rbx
0x14000c30d  push    rsi
0x14000c30e  push    rdi
0x14000c30f  push    r14
0x14000c311  sub     rsp, 90h
0x14000c318  mov     rax, cs:__security_cookie
0x14000c31f  xor     rax, rsp
0x14000c322  mov     [rsp+0A8h+var_28], rax
0x14000c32a  movzx   esi, r8b
0x14000c32e  mov     rbx, rdx
0x14000c331  mov     rdi, rcx
0x14000c334  mov     [rsp+0A8h+var_70], rcx
0x14000c339  mov     [rsp+0A8h+var_88], 0
0x14000c341  lea     r14, WPP_GLOBAL_Control
0x14000c348  mov     rcx, cs:WPP_GLOBAL_Control
0x14000c34f  cmp     rcx, r14
0x14000c352  jz      short loc_14000C36F
0x14000c354  test    byte ptr [rcx+1Ch], 8
0x14000c358  jz      short loc_14000C36F
0x14000c35a  mov     edx, 11h
0x14000c35f  lea     r8, WPP_78e66d69943b3de38e95864888fb0f14_Traceguids
0x14000c366  mov     rcx, [rcx+10h]
0x14000c36a  call    WPP_SF_
0x14000c36f  mov     [rsp+0A8h+var_80], 0
0x14000c378  cmp     qword ptr [rbx+18h], 8
0x14000c37d  jb      short loc_14000C382
0x14000c37f  mov     rbx, [rbx]
0x14000c382  mov     edx, esi
0x14000c384  lea     r8, [rsp+0A8h+var_80]
0x14000c389  mov     rcx, rbx
0x14000c38c  call    cs:__imp_AppIDEncodeAttributeString
0x14000c392  mov     ebx, eax
0x14000c394  test    eax, eax
0x14000c396  jle     short loc_14000C3A1
0x14000c398  movzx   ebx, ax
0x14000c39b  or      ebx, 80070000h
0x14000c3a1  test    ebx, ebx
0x14000c3a3  jns     short loc_14000C3ED
0x14000c3a5  mov     rcx, cs:WPP_GLOBAL_Control
0x14000c3ac  cmp     rcx, r14
0x14000c3af  jz      short loc_14000C3CF
0x14000c3b1  test    byte ptr [rcx+1Ch], 1
0x14000c3b5  jz      short loc_14000C3CF
0x14000c3b7  mov     edx, 12h
0x14000c3bc  mov     r9d, ebx
0x14000c3bf  lea     r8, WPP_78e66d69943b3de38e95864888fb0f14_Traceguids
0x14000c3c6  mov     rcx, [rcx+10h]
0x14000c3ca  call    WPP_SF_d
0x14000c3cf  mov     edx, ebx; int
0x14000c3d1  lea     rcx, [rsp+0A8h+pExceptionObject]; this
0x14000c3d6  call    ??0sddl_compiler_exception@@QEAA@J@Z; sddl_compiler_exception::sddl_compiler_exception(long)
0x14000c3db  lea     rdx, _TI4?AVsddl_compiler_exception@@; pThrowInfo
0x14000c3e2  lea     rcx, [rsp+0A8h+pExceptionObject]; pExceptionObject
0x14000c3e7  call    _CxxThrowException_0
0x14000c3ed  mov     rbx, [rsp+0A8h+var_80]
0x14000c3f2  mov     [rsp+0A8h+var_78], rbx
0x14000c3f7  mov     rdx, [rsp+0A8h+var_80]
0x14000c3fc  mov     rcx, rdi
0x14000c3ff  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@PEBG@Z; std::wstring::wstring(ushort const *)
0x14000c404  mov     [rsp+0A8h+var_88], 1
0x14000c40c  test    rbx, rbx
0x14000c40f  jz      short loc_14000C41A
0x14000c411  mov     rcx, rbx
0x14000c414  call    cs:__imp_AppIDFreeAttributeString
0x14000c41a  mov     [rsp+0A8h+var_78], 0
0x14000c423  mov     rax, rdi
0x14000c426  mov     rcx, [rsp+0A8h+var_28]
0x14000c42e  xor     rcx, rsp; StackCookie
0x14000c431  call    __security_check_cookie
0x14000c436  mov     rbx, [rsp+0A8h+arg_18]
0x14000c43e  add     rsp, 90h
0x14000c445  pop     r14
0x14000c447  pop     rdi
0x14000c448  pop     rsi
0x14000c449  retn
```
