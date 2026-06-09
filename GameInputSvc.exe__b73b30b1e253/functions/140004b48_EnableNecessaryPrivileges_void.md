# EnableNecessaryPrivileges(void)

- ea: `0x140004b48`
- end: `0x140004c18`
- name: `?EnableNecessaryPrivileges@@YAJXZ`
- size: `208`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x140004c20`

## callees

- `0x140001008`
- `0x140004b48`

## import_xrefs

- `ntdll!RtlAdjustPrivilege` at `0x140004b89`
- `ntdll!RtlAdjustPrivilege` at `0x140004b89`

## pseudocode

```c
__int64 EnableNecessaryPrivileges(void)
{
  __int64 v0; // rdi
  NTSTATUS v1; // ebx
  int v2; // r8d
  int v3; // r9d
  ULONG Privilege[8]; // [rsp+40h] [rbp-20h]
  unsigned __int8 OldValue; // [rsp+80h] [rbp+20h] BYREF
  NTSTATUS v7; // [rsp+88h] [rbp+28h] BYREF
  int v8; // [rsp+90h] [rbp+30h] BYREF
  const char *v9; // [rsp+98h] [rbp+38h] BYREF

  v0 = 0;
  Privilege[0] = 9;
  OldValue = 0;
  Privilege[1] = 17;
  Privilege[2] = 18;
  Privilege[3] = 19;
  Privilege[4] = 8;
  while ( 1 )
  {
    v1 = RtlAdjustPrivilege(Privilege[v0], 1u, 0, &OldValue);
    if ( v1 < 0 )
      break;
    v0 = (unsigned int)(v0 + 1);
    if ( (unsigned int)v0 >= 5 )
      return 0;
  }
  if ( (unsigned int)dword_14000E000 > 2
    && (qword_14000E010 & 0x800) != 0
    && (qword_14000E018 & 0x800) == qword_14000E018 )
  {
    v7 = v1;
    v9 = "onecore\\xbox\\gameinput\\published\\svc\\sfpmodify.cpp";
    v8 = 121;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_GameInputEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
      qword_14000E018,
      (unsigned int)byte_14000B669,
      v2,
      v3,
      (__int64)&v9,
      (__int64)&v8,
      (__int64)&v7);
  }
  return v1 | 0x10000000u;
}

```

## disassembly

```asm
0x140004b48  push    rbp
0x140004b4a  push    rbx
0x140004b4b  push    rdi
0x140004b4c  mov     rbp, rsp
0x140004b4f  sub     rsp, 60h
0x140004b53  xor     edi, edi
0x140004b55  mov     [rbp+Privilege], 9
0x140004b5c  mov     [rbp+OldValue], dil
0x140004b60  mov     [rbp+var_1C], 11h
0x140004b67  mov     [rbp+var_18], 12h
0x140004b6e  mov     [rbp+var_14], 13h
0x140004b75  mov     [rbp+var_10], 8
0x140004b7c  mov     ecx, [rbp+rdi*4+Privilege]; Privilege
0x140004b80  lea     r9, [rbp+OldValue]; OldValue
0x140004b84  xor     r8d, r8d; ForThread
0x140004b87  mov     dl, 1; NewValue
0x140004b89  call    cs:__imp_RtlAdjustPrivilege
0x140004b8f  mov     ebx, eax
0x140004b91  test    eax, eax
0x140004b93  js      short loc_140004BA0
0x140004b95  inc     edi
0x140004b97  cmp     edi, 5
0x140004b9a  jb      short loc_140004B7C
0x140004b9c  xor     eax, eax
0x140004b9e  jmp     short loc_140004C10
0x140004ba0  mov     eax, cs:dword_14000E000
0x140004ba6  cmp     eax, 2
0x140004ba9  jbe     short loc_140004C0A
0x140004bab  mov     rcx, cs:qword_14000E018
0x140004bb2  mov     edx, 800h
0x140004bb7  mov     rax, cs:qword_14000E010
0x140004bbe  test    rdx, rax
0x140004bc1  jz      short loc_140004C0A
0x140004bc3  mov     rax, rcx
0x140004bc6  and     rax, rdx
0x140004bc9  cmp     rax, rcx
0x140004bcc  jnz     short loc_140004C0A
0x140004bce  lea     rax, aOnecoreXboxGam_5; "onecore\\xbox\\gameinput\\published\\sv"...
0x140004bd5  mov     [rbp+arg_8], ebx
0x140004bd8  mov     [rbp+arg_18], rax
0x140004bdc  lea     rdx, byte_14000B669
0x140004be3  lea     rax, [rbp+arg_8]
0x140004be7  mov     [rbp+arg_10], 79h ; 'y'
0x140004bee  mov     [rsp+60h+var_30], rax
0x140004bf3  lea     rax, [rbp+arg_10]
0x140004bf7  mov     [rsp+60h+var_38], rax
0x140004bfc  lea     rax, [rbp+arg_18]
0x140004c00  mov     [rsp+60h+var_40], rax
0x140004c05  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_GameInputEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_GameInputEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x140004c0a  bts     ebx, 1Ch
0x140004c0e  mov     eax, ebx
0x140004c10  add     rsp, 60h
0x140004c14  pop     rdi
0x140004c15  pop     rbx
0x140004c16  pop     rbp
0x140004c17  retn
```
