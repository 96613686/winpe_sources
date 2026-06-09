# std::_Tree<std::_Tmap_traits<Sid,WpcDesktop::OTS::Manager::LocalRequestState,std::less<Sid>,std::allocator<std::pair<Sid const,WpcDesktop::OTS::Manager::LocalRequestState>>,0>>::find(Sid const &)

- ea: `0x18000dbd0`
- end: `0x18000dc73`
- name: `?find@?$_Tree@V?$_Tmap_traits@VSid@@ULocalRequestState@Manager@OTS@WpcDesktop@@U?$less@VSid@@@std@@V?$allocator@U?$pair@$$CBVSid@@ULocalRequestState@Manager@OTS@WpcDesktop@@@std@@@7@$0A@@std@@@std@@QEAA?AV?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBVSid@@ULocalRequestState@Manager@OTS@WpcDesktop@@@std@@@std@@@std@@@2@AEBVSid@@@Z`
- size: `163`
- prototype: `__int64 *__fastcall(__int64, __int64 *, __int64)`
- caller_count: `2`
- callee_count: `2`
- tags: `authz_impersonation`

## callers

- `0x18000c414`
- `0x18000d150`

## callees

- `0x180004bb0`
- `0x18000dbd0`

## pseudocode

```c
__int64 *__fastcall std::_Tree<std::_Tmap_traits<Sid,WpcDesktop::OTS::Manager::LocalRequestState,std::less<Sid>,std::allocator<std::pair<Sid const,WpcDesktop::OTS::Manager::LocalRequestState>>,0>>::find(
        __int64 a1,
        __int64 *a2,
        __int64 a3)
{
  __int64 v3; // rdi
  __int64 v6; // rbx
  const wchar_t *v7; // rsi

  v3 = WpcDesktop::OTS::Manager::PendingTimeRequests;
  v6 = *(_QWORD *)(WpcDesktop::OTS::Manager::PendingTimeRequests + 8);
  if ( *(_BYTE *)(v6 + 25) )
  {
    v7 = (const wchar_t *)(a3 + 72);
  }
  else
  {
    do
    {
      v7 = (const wchar_t *)(a3 + 72);
      if ( (unsigned __int8)std::operator<<unsigned short>((const wchar_t *)(v6 + 104), (const wchar_t *)(a3 + 72)) )
      {
        v6 += 16;
      }
      else
      {
        std::operator<<unsigned short>((const wchar_t *)(a3 + 72), (const wchar_t *)(v6 + 104));
        v3 = v6;
      }
      v6 = *(_QWORD *)v6;
    }
    while ( !*(_BYTE *)(v6 + 25) );
  }
  if ( *(_BYTE *)(v3 + 25) || (unsigned __int8)std::operator<<unsigned short>(v7, (const wchar_t *)(v3 + 104)) )
    v3 = WpcDesktop::OTS::Manager::PendingTimeRequests;
  else
    std::operator<<unsigned short>((const wchar_t *)(v3 + 104), v7);
  *a2 = v3;
  return a2;
}

```

## disassembly

```asm
0x18000dbd0  mov     [rsp+arg_0], rcx
0x18000dbd5  push    rbx
0x18000dbd6  push    rbp
0x18000dbd7  push    rsi
0x18000dbd8  push    rdi
0x18000dbd9  push    r14
0x18000dbdb  push    r15
0x18000dbdd  sub     rsp, 48h
0x18000dbe1  mov     rdi, cs:?PendingTimeRequests@Manager@OTS@WpcDesktop@@3V?$map@VSid@@ULocalRequestState@Manager@OTS@WpcDesktop@@U?$less@VSid@@@std@@V?$allocator@U?$pair@$$CBVSid@@ULocalRequestState@Manager@OTS@WpcDesktop@@@std@@@7@@std@@A; std::map<Sid,WpcDesktop::OTS::Manager::LocalRequestState> WpcDesktop::OTS::Manager::PendingTimeRequests
0x18000dbe8  xor     eax, eax
0x18000dbea  mov     rbp, r8
0x18000dbed  mov     [rsp+78h+var_4C], eax
0x18000dbf1  mov     r14, rdx
0x18000dbf4  mov     rbx, [rdi+8]
0x18000dbf8  cmp     [rbx+19h], al
0x18000dbfb  jnz     short loc_18000DC31
0x18000dbfd  lea     rsi, [rbp+48h]
0x18000dc01  mov     rdx, rsi
0x18000dc04  lea     rcx, [rbx+68h]
0x18000dc08  call    ??$?MGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA_NAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@0@Z; std::operator<<ushort>(std::wstring const &,std::wstring const &)
0x18000dc0d  test    al, al
0x18000dc0f  jz      short loc_18000DC17
0x18000dc11  add     rbx, 10h
0x18000dc15  jmp     short loc_18000DC26
0x18000dc17  lea     rdx, [rbx+68h]
0x18000dc1b  mov     rcx, rsi
0x18000dc1e  call    ??$?MGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA_NAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@0@Z; std::operator<<ushort>(std::wstring const &,std::wstring const &)
0x18000dc23  mov     rdi, rbx
0x18000dc26  mov     rbx, [rbx]
0x18000dc29  cmp     byte ptr [rbx+19h], 0
0x18000dc2d  jz      short loc_18000DBFD
0x18000dc2f  jmp     short loc_18000DC35
0x18000dc31  lea     rsi, [r8+48h]
0x18000dc35  cmp     byte ptr [rdi+19h], 0
0x18000dc39  jnz     short loc_18000DC59
0x18000dc3b  lea     rdx, [rdi+68h]
0x18000dc3f  mov     rcx, rsi
0x18000dc42  call    ??$?MGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA_NAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@0@Z; std::operator<<ushort>(std::wstring const &,std::wstring const &)
0x18000dc47  test    al, al
0x18000dc49  jnz     short loc_18000DC59
0x18000dc4b  mov     rdx, rsi
0x18000dc4e  lea     rcx, [rdi+68h]
0x18000dc52  call    ??$?MGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA_NAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@0@Z; std::operator<<ushort>(std::wstring const &,std::wstring const &)
0x18000dc57  jmp     short loc_18000DC60
0x18000dc59  mov     rdi, cs:?PendingTimeRequests@Manager@OTS@WpcDesktop@@3V?$map@VSid@@ULocalRequestState@Manager@OTS@WpcDesktop@@U?$less@VSid@@@std@@V?$allocator@U?$pair@$$CBVSid@@ULocalRequestState@Manager@OTS@WpcDesktop@@@std@@@7@@std@@A; std::map<Sid,WpcDesktop::OTS::Manager::LocalRequestState> WpcDesktop::OTS::Manager::PendingTimeRequests
0x18000dc60  mov     [r14], rdi
0x18000dc63  mov     rax, r14
0x18000dc66  add     rsp, 48h
0x18000dc6a  pop     r15
0x18000dc6c  pop     r14
0x18000dc6e  pop     rdi
0x18000dc6f  pop     rsi
0x18000dc70  pop     rbp
0x18000dc71  pop     rbx
0x18000dc72  retn
```
