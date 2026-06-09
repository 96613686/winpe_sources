# CUserName::GetUserSid(_SID * *)

- ea: `0x18005ab50`
- end: `0x18005ac0c`
- name: `?GetUserSid@CUserName@@UEAAJPEAPEAU_SID@@@Z`
- size: `188`
- prototype: `__int64 __fastcall(CUserName *__hidden this, struct _SID **)`
- caller_count: `0`
- callee_count: `4`
- tags: `authz_impersonation, loader_planting, service_task, broker_com_uri`

## callees

- `0x180003f30`
- `0x1800178e0`
- `0x18001b46d`
- `0x18005ab50`

## import_xrefs

- `ntdll!RtlLengthSid` at `0x18005abc4`
- `ntdll!RtlLengthSid` at `0x18005abc4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18005abce`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18005abce`

## string_xrefs

- `0x18005ab73`: `No token`
- `0x18005ab9d`: `CUserName::GetUserSid`

## pseudocode

```c
__int64 __fastcall CUserName::GetUserSid(CUserName *this, struct _SID **a2)
{
  int v2; // eax
  unsigned int v5; // ebx
  int v6; // eax
  SIZE_T v7; // rbx
  struct _SID *v8; // rax

  v2 = *((_DWORD *)this + 400);
  if ( (v2 & 2) == 0 )
  {
    if ( (v2 & 1) == 0 )
    {
      _DbgPrintMessage(8, "No token");
      return (unsigned int)-2147023888;
    }
    v6 = CUserName::InitializeUserName(this, *((void **)this + 199));
    v5 = v6;
    if ( v6 < 0 )
    {
      _DbgPrintMessage(8, "InitializeUserName failed: 0x%x in %s", v6, "CUserName::GetUserSid");
      return v5;
    }
  }
  v7 = RtlLengthSid(**((PSID **)this + 201));
  v8 = (struct _SID *)CoTaskMemAlloc(v7);
  if ( v8 )
  {
    *a2 = v8;
    memcpy_0(v8, **((const void ***)this + 201), v7);
    return 0;
  }
  else
  {
    return (unsigned int)-2147024882;
  }
}

```

## disassembly

```asm
0x18005ab50  mov     [rsp+arg_0], rbx
0x18005ab55  mov     [rsp+arg_8], rsi
0x18005ab5a  push    rdi
0x18005ab5b  sub     rsp, 20h
0x18005ab5f  mov     eax, [rcx+640h]
0x18005ab65  mov     rsi, rdx
0x18005ab68  mov     rdi, rcx
0x18005ab6b  test    al, 2
0x18005ab6d  jnz     short loc_18005ABBA
0x18005ab6f  test    al, 1
0x18005ab71  jnz     short loc_18005AB8B
0x18005ab73  lea     rdx, aNoToken; "No token"
0x18005ab7a  mov     ecx, 8; int
0x18005ab7f  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18005ab84  mov     ebx, 800703F0h
0x18005ab89  jmp     short loc_18005ABFA
0x18005ab8b  mov     rdx, [rcx+638h]; void *
0x18005ab92  call    ?InitializeUserName@CUserName@@AEAAJPEAX@Z; CUserName::InitializeUserName(void *)
0x18005ab97  mov     ebx, eax
0x18005ab99  test    eax, eax
0x18005ab9b  jns     short loc_18005ABBA
0x18005ab9d  lea     r9, aCusernameGetus_0; "CUserName::GetUserSid"
0x18005aba4  mov     r8d, eax
0x18005aba7  lea     rdx, aInitializeuser; "InitializeUserName failed: 0x%x in %s"
0x18005abae  mov     ecx, 8; int
0x18005abb3  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18005abb8  jmp     short loc_18005ABFA
0x18005abba  mov     rcx, [rdi+648h]
0x18005abc1  mov     rcx, [rcx]; Sid
0x18005abc4  call    cs:__imp_RtlLengthSid
0x18005abca  mov     ecx, eax; cb
0x18005abcc  mov     ebx, eax
0x18005abce  call    cs:__imp_CoTaskMemAlloc
0x18005abd4  test    rax, rax
0x18005abd7  jnz     short loc_18005ABE0
0x18005abd9  mov     ebx, 8007000Eh
0x18005abde  jmp     short loc_18005ABFA
0x18005abe0  mov     [rsi], rax
0x18005abe3  mov     r8, rbx; Size
0x18005abe6  mov     rdx, [rdi+648h]
0x18005abed  mov     rcx, rax; void *
0x18005abf0  mov     rdx, [rdx]; Src
0x18005abf3  call    memcpy_0
0x18005abf8  xor     ebx, ebx
0x18005abfa  mov     rsi, [rsp+28h+arg_8]
0x18005abff  mov     eax, ebx
0x18005ac01  mov     rbx, [rsp+28h+arg_0]
0x18005ac06  add     rsp, 20h
0x18005ac0a  pop     rdi
0x18005ac0b  retn
```
