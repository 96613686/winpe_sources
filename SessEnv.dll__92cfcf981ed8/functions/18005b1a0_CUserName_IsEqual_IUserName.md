# CUserName::IsEqual(IUserName *)

- ea: `0x18005b1a0`
- end: `0x18005b274`
- name: `?IsEqual@CUserName@@UEAAJPEAUIUserName@@@Z`
- size: `212`
- prototype: `__int64 __fastcall(CUserName *__hidden this, struct IUserName *)`
- caller_count: `0`
- callee_count: `4`
- tags: `authz_impersonation, loader_planting, service_task, broker_com_uri`

## callees

- `0x180003f30`
- `0x1800178e0`
- `0x18005b1a0`
- `0x18005d010`

## import_xrefs

- `ntdll!RtlEqualSid` at `0x18005b245`
- `ntdll!RtlEqualSid` at `0x18005b245`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18005b25c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18005b25c`

## string_xrefs

- `0x18005b1cc`: `No token`
- `0x18005b22d`: `GetUserSid failed: 0x%x in %s`

## pseudocode

```c
__int64 __fastcall CUserName::IsEqual(CUserName *this, struct IUserName *a2)
{
  int v2; // eax
  unsigned int v5; // ebx
  int v6; // eax
  int v7; // eax
  PSID Sid2; // [rsp+30h] [rbp+8h] BYREF

  v2 = *((_DWORD *)this + 400);
  Sid2 = 0;
  if ( (v2 & 2) != 0 )
    goto LABEL_7;
  if ( (v2 & 1) == 0 )
  {
    _DbgPrintMessage(8, "No token");
    v5 = -2147023888;
    goto LABEL_10;
  }
  v6 = CUserName::InitializeUserName(this, *((void **)this + 199));
  v5 = v6;
  if ( v6 >= 0 )
  {
LABEL_7:
    v7 = (*(__int64 (__fastcall **)(struct IUserName *, PSID *))(*(_QWORD *)a2 + 72LL))(a2, &Sid2);
    v5 = v7;
    if ( v7 >= 0 )
      v5 = RtlEqualSid(**((PSID **)this + 201), Sid2) == 0;
    else
      _DbgPrintMessage(8, "GetUserSid failed: 0x%x in %s", (unsigned int)v7, "CUserName::IsEqual");
  }
  else
  {
    _DbgPrintMessage(8, "InitializeUserName failed: 0x%x in %s", (unsigned int)v6, "CUserName::IsEqual");
  }
LABEL_10:
  if ( Sid2 )
    CoTaskMemFree(Sid2);
  return v5;
}

```

## disassembly

```asm
0x18005b1a0  mov     [rsp+arg_8], rbx
0x18005b1a5  mov     [rsp+arg_10], rsi
0x18005b1aa  push    rdi
0x18005b1ab  sub     rsp, 20h
0x18005b1af  mov     eax, [rcx+640h]
0x18005b1b5  mov     rsi, rdx
0x18005b1b8  mov     [rsp+28h+Sid2], 0
0x18005b1c1  mov     rdi, rcx
0x18005b1c4  test    al, 2
0x18005b1c6  jnz     short loc_18005B213
0x18005b1c8  test    al, 1
0x18005b1ca  jnz     short loc_18005B1E4
0x18005b1cc  lea     rdx, aNoToken; "No token"
0x18005b1d3  mov     ecx, 8; int
0x18005b1d8  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18005b1dd  mov     ebx, 800703F0h
0x18005b1e2  jmp     short loc_18005B252
0x18005b1e4  mov     rdx, [rcx+638h]; void *
0x18005b1eb  call    ?InitializeUserName@CUserName@@AEAAJPEAX@Z; CUserName::InitializeUserName(void *)
0x18005b1f0  mov     ebx, eax
0x18005b1f2  test    eax, eax
0x18005b1f4  jns     short loc_18005B213
0x18005b1f6  lea     rdx, aInitializeuser; "InitializeUserName failed: 0x%x in %s"
0x18005b1fd  mov     r8d, eax
0x18005b200  lea     r9, aCusernameIsequ; "CUserName::IsEqual"
0x18005b207  mov     ecx, 8; int
0x18005b20c  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18005b211  jmp     short loc_18005B252
0x18005b213  mov     rax, [rsi]
0x18005b216  lea     rdx, [rsp+28h+Sid2]
0x18005b21b  mov     rcx, rsi
0x18005b21e  mov     rax, [rax+48h]
0x18005b222  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005b227  mov     ebx, eax
0x18005b229  test    eax, eax
0x18005b22b  jns     short loc_18005B236
0x18005b22d  lea     rdx, aGetusersidFail; "GetUserSid failed: 0x%x in %s"
0x18005b234  jmp     short loc_18005B1FD
0x18005b236  mov     rcx, [rdi+648h]
0x18005b23d  mov     rdx, [rsp+28h+Sid2]; Sid2
0x18005b242  mov     rcx, [rcx]; Sid1
0x18005b245  call    cs:__imp_RtlEqualSid
0x18005b24b  xor     ebx, ebx
0x18005b24d  test    al, al
0x18005b24f  setz    bl
0x18005b252  mov     rcx, [rsp+28h+Sid2]; pv
0x18005b257  test    rcx, rcx
0x18005b25a  jz      short loc_18005B262
0x18005b25c  call    cs:__imp_CoTaskMemFree
0x18005b262  mov     rsi, [rsp+28h+arg_10]
0x18005b267  mov     eax, ebx
0x18005b269  mov     rbx, [rsp+28h+arg_8]
0x18005b26e  add     rsp, 20h
0x18005b272  pop     rdi
0x18005b273  retn
```
