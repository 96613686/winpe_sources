# MidiLoopbackDeviceTable::RemoveDevice(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>)

- ea: `0x180017e9c`
- end: `0x180017fcb`
- name: `?RemoveDevice@MidiLoopbackDeviceTable@@QEAAXV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z`
- size: `303`
- prototype: `void __fastcall(_QWORD *, void *)`
- caller_count: `1`
- callee_count: `9`
- tags: `service_task`

## callers

- `0x180018710`

## callees

- `0x180004180`
- `0x18000b740`
- `0x18000e4f8`
- `0x18000f0a4`
- `0x180013294`
- `0x180014ab8`
- `0x180017e9c`
- `0x18001b66c`
- `0x180032010`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall MidiLoopbackDeviceTable::RemoveDevice(_QWORD *a1, void *a2)
{
  __int64 v4; // rax
  __int64 v5; // rbx
  const wchar_t *v6; // rdx
  size_t v7; // rdi
  size_t v8; // r14
  const wchar_t *v9; // rcx
  size_t v10; // r8
  int v11; // eax
  __int64 v12; // rcx
  __int64 v13; // rcx
  _BYTE v14[16]; // [rsp+28h] [rbp-58h] BYREF
  __int64 v15; // [rsp+38h] [rbp-48h]
  void *v16; // [rsp+48h] [rbp-38h]
  wchar_t *S1[2]; // [rsp+50h] [rbp-30h] BYREF
  size_t N; // [rsp+60h] [rbp-20h]
  unsigned __int64 v19; // [rsp+68h] [rbp-18h]

  v16 = a2;
  v4 = std::wstring::wstring(v14, a2);
  WindowsMidiServicesInternal::ToLowerTrimmedWStringCopy(S1, v4);
  std::_Tree<std::_Tmap_traits<std::wstring,bool,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,bool>>,0>>::_Find_lower_bound<std::wstring>(
    a1,
    v14,
    S1);
  v5 = v15;
  if ( !*(_BYTE *)(v15 + 25) )
  {
    v6 = (const wchar_t *)(v15 + 32);
    v7 = *(_QWORD *)(v15 + 48);
    if ( *(_QWORD *)(v15 + 56) > 7u )
      v6 = *(const wchar_t **)v6;
    v8 = N;
    v9 = (const wchar_t *)S1;
    if ( v19 > 7 )
      v9 = S1[0];
    v10 = *(_QWORD *)(v15 + 48);
    if ( v7 >= N )
      v10 = N;
    v11 = wmemcmp(v9, v6, v10);
    if ( v11 )
    {
      if ( v11 < 0 )
        goto LABEL_18;
    }
    else if ( v8 < v7 )
    {
      goto LABEL_18;
    }
    if ( v5 != *a1 )
    {
      v12 = *(_QWORD *)(v5 + 528);
      if ( v12 )
      {
        *(_QWORD *)(v5 + 528) = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v12 + 16LL))(v12);
      }
      v13 = *(_QWORD *)(v5 + 536);
      if ( v13 )
      {
        *(_QWORD *)(v5 + 536) = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v13 + 16LL))(v13);
      }
      std::_Tree<std::_Tmap_traits<std::wstring,MidiLoopbackDevice,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,MidiLoopbackDevice>>,0>>::erase(
        a1,
        S1);
    }
  }
LABEL_18:
  std::wstring::~wstring(S1);
  std::wstring::~wstring(a2);
}

```

## disassembly

```asm
0x180017e9c  mov     [rsp-28h+arg_10], rbx
0x180017ea1  push    rbp
0x180017ea2  push    rsi
0x180017ea3  push    rdi
0x180017ea4  push    r14
0x180017ea6  push    r15
0x180017ea8  mov     rbp, rsp
0x180017eab  sub     rsp, 80h
0x180017eb2  mov     rax, cs:__security_cookie
0x180017eb9  xor     rax, rsp
0x180017ebc  mov     [rbp+var_10], rax
0x180017ec0  mov     r15, rdx
0x180017ec3  mov     rsi, rcx
0x180017ec6  mov     [rbp+var_38], rdx
0x180017eca  lea     rcx, [rbp+var_58]
0x180017ece  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x180017ed3  mov     rdx, rax
0x180017ed6  lea     rcx, [rbp+S1]
0x180017eda  call    ?ToLowerTrimmedWStringCopy@WindowsMidiServicesInternal@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V23@@Z; WindowsMidiServicesInternal::ToLowerTrimmedWStringCopy(std::wstring)
0x180017edf  lea     r8, [rbp+S1]
0x180017ee3  lea     rdx, [rbp+var_58]
0x180017ee7  mov     rcx, rsi
0x180017eea  call    ??$_Find_lower_bound@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@?$_Tree@V?$_Tmap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@_NU?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@_N@std@@@2@$0A@@std@@@std@@IEBA?AU?$_Tree_find_result@PEAU?$_Tree_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@_N@std@@PEAX@std@@@1@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@@Z; std::_Tree<std::_Tmap_traits<std::wstring,bool,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,bool>>,0>>::_Find_lower_bound<std::wstring>(std::wstring const &)
0x180017eef  mov     rbx, [rbp+var_48]
0x180017ef3  cmp     byte ptr [rbx+19h], 0
0x180017ef7  jnz     loc_180017F96
0x180017efd  lea     rdx, [rbx+20h]
0x180017f01  mov     rdi, [rdx+10h]
0x180017f05  cmp     qword ptr [rdx+18h], 7
0x180017f0a  jbe     short loc_180017F0F
0x180017f0c  mov     rdx, [rdx]; S2
0x180017f0f  mov     r14, [rbp+N]
0x180017f13  lea     rcx, [rbp+S1]
0x180017f17  cmp     [rbp+var_18], 7
0x180017f1c  cmova   rcx, [rbp+S1]; S1
0x180017f21  mov     r8, rdi
0x180017f24  cmp     rdi, r14
0x180017f27  cmovnb  r8, r14; N
0x180017f2b  call    wmemcmp
0x180017f30  test    eax, eax
0x180017f32  jnz     short loc_180017F3B
0x180017f34  cmp     r14, rdi
0x180017f37  jnb     short loc_180017F3D
0x180017f39  jmp     short loc_180017F96
0x180017f3b  js      short loc_180017F96
0x180017f3d  cmp     rbx, [rsi]
0x180017f40  jz      short loc_180017F96
0x180017f42  mov     rcx, [rbx+210h]
0x180017f49  test    rcx, rcx
0x180017f4c  jz      short loc_180017F66
0x180017f4e  mov     qword ptr [rbx+210h], 0
0x180017f59  mov     rax, [rcx]
0x180017f5c  mov     rax, [rax+10h]
0x180017f60  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017f65  nop
0x180017f66  mov     rcx, [rbx+218h]
0x180017f6d  test    rcx, rcx
0x180017f70  jz      short loc_180017F8A
0x180017f72  mov     qword ptr [rbx+218h], 0
0x180017f7d  mov     rax, [rcx]
0x180017f80  mov     rax, [rax+10h]
0x180017f84  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017f89  nop
0x180017f8a  lea     rdx, [rbp+S1]
0x180017f8e  mov     rcx, rsi
0x180017f91  call    ?erase@?$_Tree@V?$_Tmap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@VMidiLoopbackDevice@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@VMidiLoopbackDevice@@@std@@@2@$0A@@std@@@std@@QEAA_KAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@2@@Z; std::_Tree<std::_Tmap_traits<std::wstring,MidiLoopbackDevice,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,MidiLoopbackDevice>>,0>>::erase(std::wstring const &)
0x180017f96  lea     rcx, [rbp+S1]; void *
0x180017f9a  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180017f9f  nop
0x180017fa0  mov     rcx, r15; void *
0x180017fa3  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180017fa8  mov     rcx, [rbp+var_10]
0x180017fac  xor     rcx, rsp; StackCookie
0x180017faf  call    __security_check_cookie
0x180017fb4  mov     rbx, [rsp+80h+arg_10]
0x180017fbc  add     rsp, 80h
0x180017fc3  pop     r15
0x180017fc5  pop     r14
0x180017fc7  pop     rdi
0x180017fc8  pop     rsi
0x180017fc9  pop     rbp
0x180017fca  retn
```
