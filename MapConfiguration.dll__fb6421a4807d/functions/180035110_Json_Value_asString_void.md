# Json::Value::asString(void)

- ea: `0x180035110`
- end: `0x18003524d`
- name: `?asString@Value@Json@@QEBA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@XZ`
- size: `317`
- prototype: ``
- caller_count: `6`
- callee_count: `11`
- tags: `registry_config`

## callers

- `0x1800210ac`
- `0x1800219fc`
- `0x1800222e4`
- `0x180022764`
- `0x18002546c`
- `0x180038984`

## callees

- `0x1800094a0`
- `0x18000c850`
- `0x18001a7a8`
- `0x18002f858`
- `0x180033fb0`
- `0x180035110`
- `0x180035594`
- `0x1800360f0`
- `0x18003a4b8`
- `0x18003a63c`
- `0x18003a6cc`

## import_xrefs

- `msvcp_win!??6?$basic_ostream@DU?$char_traits@D@std@@@std@@QEAAAEAV01@PEBX@Z` at `0x18003517e`
- `msvcp_win!??6?$basic_ostream@DU?$char_traits@D@std@@@std@@QEAAAEAV01@PEBX@Z` at `0x18003517e`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall Json::Value::asString(_QWORD *a1, __int64 a2)
{
  const wchar_t *v3; // rdx
  __int64 v4; // rdx
  __int64 v5; // rcx
  unsigned int v7; // [rsp+20h] [rbp-148h] BYREF
  __int64 v8[3]; // [rsp+28h] [rbp-140h] BYREF
  _BYTE v9[8]; // [rsp+40h] [rbp-128h] BYREF
  _BYTE v10[232]; // [rsp+48h] [rbp-120h] BYREF
  _BYTE v11[32]; // [rsp+130h] [rbp-38h] BYREF

  v8[0] = a2;
  switch ( *((_BYTE *)a1 + 8) )
  {
    case 0:
      goto LABEL_16;
    case 1:
      Json::valueToString(a2, *a1);
      return a2;
    case 2:
      Json::valueToString(a2, *a1);
      return a2;
    case 3:
      Json::valueToString(a2);
      return a2;
  }
  if ( *((_BYTE *)a1 + 8) != 4 )
  {
    if ( *((_BYTE *)a1 + 8) != 5 )
    {
      std::ostringstream::ostringstream((__int64)v9);
      std::ostream::operator<<(v9, L"Type is not convertible to string");
      std::stringbuf::str(v10, v11);
      Json::throwLogicError(v11);
    }
    v3 = L"true";
    if ( !*(_BYTE *)a1 )
      v3 = L"false";
    goto LABEL_17;
  }
  v4 = *a1;
  if ( !*a1 )
  {
LABEL_16:
    v3 = (const wchar_t *)&qword_180048C70;
LABEL_17:
    std::wstring::wstring(a2, (__int64)v3);
    return a2;
  }
  v7 = 0;
  v8[0] = 0;
  v5 = *((_DWORD *)a1 + 2) >> 8;
  LOBYTE(v5) = v5 & 1;
  Json::decodePrefixedString(v5, v4, &v7, v8);
  std::wstring::wstring(a2, v8[0], v7);
  return a2;
}

```

## disassembly

```asm
0x180035110  push    rbx
0x180035112  sub     rsp, 160h
0x180035119  mov     rax, cs:__security_cookie
0x180035120  xor     rax, rsp
0x180035123  mov     [rsp+168h+var_18], rax
0x18003512b  mov     rbx, rdx
0x18003512e  mov     [rsp+168h+var_140], rdx
0x180035133  xor     r8d, r8d
0x180035136  movsx   edx, byte ptr [rcx+8]
0x18003513a  test    edx, edx
0x18003513c  jz      loc_180035222
0x180035142  sub     edx, 1
0x180035145  jz      loc_180035215
0x18003514b  sub     edx, 1
0x18003514e  jz      loc_180035208
0x180035154  sub     edx, 1
0x180035157  jz      loc_1800351FA
0x18003515d  sub     edx, 1
0x180035160  jz      short loc_1800351BC
0x180035162  cmp     edx, 1
0x180035165  jz      short loc_1800351A5
0x180035167  lea     rcx, [rsp+168h+var_128]
0x18003516c  call    ??0?$basic_ostringstream@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::ostringstream::ostringstream(void)
0x180035171  nop
0x180035172  lea     rdx, aTypeIsNotConve; "Type is not convertible to string"
0x180035179  lea     rcx, [rsp+168h+var_128]
0x18003517e  call    cs:__imp_??6?$basic_ostream@DU?$char_traits@D@std@@@std@@QEAAAEAV01@PEBX@Z; std::ostream::operator<<(void const *)
0x180035184  lea     rdx, [rsp+168h+var_38]
0x18003518c  lea     rcx, [rsp+168h+var_120]
0x180035191  call    ?str@?$basic_stringbuf@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEBA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@XZ; std::stringbuf::str(void)
0x180035196  nop
0x180035197  lea     rcx, [rsp+168h+var_38]
0x18003519f  call    ?throwLogicError@Json@@YAXAEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@Z; Json::throwLogicError(std::string const &)
0x1800351a5  lea     rax, aFalse; "false"
0x1800351ac  lea     rdx, aTrue; "true"
0x1800351b3  cmp     [rcx], r8b
0x1800351b6  cmovz   rdx, rax
0x1800351ba  jmp     short loc_180035229
0x1800351bc  mov     rdx, [rcx]
0x1800351bf  test    rdx, rdx
0x1800351c2  jz      short loc_180035222
0x1800351c4  mov     [rsp+168h+var_148], r8d
0x1800351c9  mov     [rsp+168h+var_140], r8
0x1800351ce  mov     ecx, [rcx+8]
0x1800351d1  shr     ecx, 8
0x1800351d4  and     cl, 1
0x1800351d7  lea     r9, [rsp+168h+var_140]
0x1800351dc  lea     r8, [rsp+168h+var_148]
0x1800351e1  call    Json__decodePrefixedString
0x1800351e6  mov     r8d, [rsp+168h+var_148]
0x1800351eb  mov     rdx, [rsp+168h+var_140]
0x1800351f0  mov     rcx, rbx
0x1800351f3  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG_K@Z; std::wstring::wstring(ushort const * const,unsigned __int64)
0x1800351f8  jmp     short loc_180035231
0x1800351fa  movsd   xmm1, qword ptr [rcx]
0x1800351fe  mov     rcx, rbx
0x180035201  call    ?valueToString@Json@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@N@Z; Json::valueToString(double)
0x180035206  jmp     short loc_180035231
0x180035208  mov     rdx, [rcx]
0x18003520b  mov     rcx, rbx
0x18003520e  call    ?valueToString@Json@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@_K@Z; Json::valueToString(unsigned __int64)
0x180035213  jmp     short loc_180035231
0x180035215  mov     rdx, [rcx]
0x180035218  mov     rcx, rbx
0x18003521b  call    ?valueToString@Json@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@_J@Z; Json::valueToString(__int64)
0x180035220  jmp     short loc_180035231
0x180035222  lea     rdx, qword_180048C70
0x180035229  mov     rcx, rbx
0x18003522c  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180035231  mov     rax, rbx
0x180035234  mov     rcx, [rsp+168h+var_18]
0x18003523c  xor     rcx, rsp; StackCookie
0x18003523f  call    __security_check_cookie
0x180035244  add     rsp, 160h
0x18003524b  pop     rbx
0x18003524c  retn
```
