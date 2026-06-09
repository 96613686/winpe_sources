# AxISEvents::GenerateUrlPolicyEvent(_EVENT_DESCRIPTOR const *,ushort const *,ushort const *)

- ea: `0x1800072f4`
- end: `0x1800073b9`
- name: `?GenerateUrlPolicyEvent@AxISEvents@@QEAAKPEBU_EVENT_DESCRIPTOR@@PEBG1@Z`
- size: `197`
- prototype: `unsigned int __fastcall(AxISEvents *__hidden this, const struct _EVENT_DESCRIPTOR *, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180005ee0`

## callees

- `0x180001720`
- `0x1800072f4`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventWrite` at `0x18000739c`
- `api-ms-win-eventing-provider-l1-1-0!EventWrite` at `0x18000739c`

## pseudocode

```c
ULONG __fastcall AxISEvents::GenerateUrlPolicyEvent(
        AxISEvents *this,
        const struct _EVENT_DESCRIPTOR *a2,
        const unsigned __int16 *a3,
        const unsigned __int16 *a4)
{
  ULONG result; // eax
  __int64 v6; // rcx
  __int64 v7; // rax
  _EVENT_DATA_DESCRIPTOR UserData; // [rsp+20h] [rbp-30h] BYREF
  const wchar_t *v9; // [rsp+30h] [rbp-20h]
  __int64 v10; // [rsp+38h] [rbp-18h]

  result = 0;
  if ( *((_DWORD *)this + 2) )
  {
    v6 = -1;
    if ( a3 )
    {
      UserData.Ptr = (ULONGLONG)a3;
      v7 = -1;
      do
        ++v7;
      while ( a3[v7] );
      UserData.Reserved = 0;
      UserData.Size = 2 * v7 + 2;
    }
    else
    {
      UserData.Ptr = (ULONGLONG)L"<Unknown>";
      *(_QWORD *)&UserData.Size = 20;
    }
    if ( a4 )
    {
      v9 = a4;
      do
        ++v6;
      while ( a4[v6] );
      v10 = (unsigned int)(2 * v6 + 2);
    }
    else
    {
      v9 = L"<Unknown>";
      v10 = 20;
    }
    return EventWrite(*((_QWORD *)this + 4), a2, 2u, &UserData);
  }
  return result;
}

```

## disassembly

```asm
0x1800072f4  mov     [rsp-8+arg_10], rbx
0x1800072f9  push    rbp
0x1800072fa  mov     rbp, rsp
0x1800072fd  sub     rsp, 50h
0x180007301  mov     rax, cs:__security_cookie
0x180007308  xor     rax, rsp
0x18000730b  mov     [rbp+var_10], rax
0x18000730f  xor     r11d, r11d
0x180007312  mov     r10, rcx
0x180007315  mov     eax, r11d
0x180007318  cmp     [rcx+8], r11d
0x18000731c  jz      loc_1800073A2
0x180007322  or      rcx, 0FFFFFFFFFFFFFFFFh
0x180007326  lea     rbx, aUnknown; "<Unknown>"
0x18000732d  test    r8, r8
0x180007330  jz      short loc_180007353
0x180007332  mov     [rbp+UserData.Ptr], r8
0x180007336  mov     rax, rcx
0x180007339  inc     rax
0x18000733c  cmp     [r8+rax*2], r11w
0x180007341  jnz     short loc_180007339
0x180007343  lea     eax, ds:2[rax*2]
0x18000734a  mov     dword ptr [rbp+UserData.0Ch], r11d
0x18000734e  mov     [rbp+UserData.Size], eax
0x180007351  jmp     short loc_18000735F
0x180007353  mov     [rbp+UserData.Ptr], rbx
0x180007357  mov     qword ptr [rbp+UserData.Size], 14h
0x18000735f  test    r9, r9
0x180007362  jz      short loc_180007382
0x180007364  mov     [rbp+var_20], r9
0x180007368  inc     rcx
0x18000736b  cmp     [r9+rcx*2], r11w
0x180007370  jnz     short loc_180007368
0x180007372  lea     eax, ds:2[rcx*2]
0x180007379  mov     dword ptr [rbp+var_18+4], r11d
0x18000737d  mov     dword ptr [rbp+var_18], eax
0x180007380  jmp     short loc_18000738E
0x180007382  mov     [rbp+var_20], rbx
0x180007386  mov     [rbp+var_18], 14h
0x18000738e  mov     rcx, [r10+20h]; RegHandle
0x180007392  lea     r9, [rbp+UserData]; UserData
0x180007396  mov     r8d, 2; UserDataCount
0x18000739c  call    cs:__imp_EventWrite
0x1800073a2  mov     rcx, [rbp+var_10]
0x1800073a6  xor     rcx, rsp; StackCookie
0x1800073a9  call    __security_check_cookie
0x1800073ae  mov     rbx, [rsp+50h+arg_10]
0x1800073b3  add     rsp, 50h
0x1800073b7  pop     rbp
0x1800073b8  retn
```
