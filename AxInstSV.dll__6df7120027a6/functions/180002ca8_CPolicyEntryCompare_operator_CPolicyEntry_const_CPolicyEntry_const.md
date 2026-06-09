# CPolicyEntryCompare::operator()(CPolicyEntry * const &,CPolicyEntry * const &)

- ea: `0x180002ca8`
- end: `0x180002da4`
- name: `??RCPolicyEntryCompare@@QEBA_NAEBQEAVCPolicyEntry@@0@Z`
- size: `252`
- prototype: `bool __fastcall(__int64, __int64, __int64)`
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800028f4`
- `0x180002978`

## callees

- `0x180002ca8`
- `0x180015010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180002d7a`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180002d7a`
- `OLEAUT32!__imp_SysFreeString` at `0x180002d89`
- `OLEAUT32!__imp_SysFreeString` at `0x180002d94`
- `OLEAUT32!__imp_SysFreeString` at `0x180002d89`
- `OLEAUT32!__imp_SysFreeString` at `0x180002d94`
- `OLEAUT32!__imp_SysStringLen` at `0x180002d4e`
- `OLEAUT32!__imp_SysStringLen` at `0x180002d5a`
- `OLEAUT32!__imp_SysStringLen` at `0x180002d4e`
- `OLEAUT32!__imp_SysStringLen` at `0x180002d5a`

## pseudocode

```c
bool __fastcall CPolicyEntryCompare::operator()(__int64 a1, __int64 a2, __int64 a3)
{
  bool v5; // bl
  UINT v6; // ebx
  UINT v7; // eax
  unsigned int v9; // [rsp+40h] [rbp+20h] BYREF
  int v10; // [rsp+44h] [rbp+24h]
  unsigned int v11; // [rsp+48h] [rbp+28h] BYREF
  BSTR bstrString; // [rsp+50h] [rbp+30h] BYREF
  BSTR pbstr; // [rsp+58h] [rbp+38h] BYREF

  v10 = HIDWORD(a1);
  v9 = 0;
  v11 = 0;
  pbstr = 0;
  bstrString = 0;
  (*(void (__fastcall **)(_QWORD, unsigned int *))(**(_QWORD **)(*(_QWORD *)a2 + 16LL) + 192LL))(
    *(_QWORD *)(*(_QWORD *)a2 + 16LL),
    &v9);
  (*(void (__fastcall **)(_QWORD, unsigned int *))(**(_QWORD **)(*(_QWORD *)a3 + 16LL) + 192LL))(
    *(_QWORD *)(*(_QWORD *)a3 + 16LL),
    &v11);
  if ( v9 == v11 )
  {
    (*(void (__fastcall **)(_QWORD, BSTR *))(**(_QWORD **)(*(_QWORD *)a2 + 16LL) + 104LL))(
      *(_QWORD *)(*(_QWORD *)a2 + 16LL),
      &pbstr);
    (*(void (__fastcall **)(_QWORD, BSTR *))(**(_QWORD **)(*(_QWORD *)a3 + 16LL) + 104LL))(
      *(_QWORD *)(*(_QWORD *)a3 + 16LL),
      &bstrString);
    v6 = SysStringLen(pbstr);
    v7 = SysStringLen(bstrString);
    v5 = v6 < v7 || v6 <= v7 && v6 && (int)_o__wcsicmp(pbstr, bstrString) < 0;
  }
  else
  {
    v5 = v9 < v11;
  }
  SysFreeString(bstrString);
  SysFreeString(pbstr);
  return v5;
}

```

## disassembly

```asm
0x180002ca8  mov     [rsp-18h+arg_0], rcx
0x180002cad  push    rbp
0x180002cae  push    rbx
0x180002caf  push    rdi
0x180002cb0  mov     rbp, rsp
0x180002cb3  sub     rsp, 20h
0x180002cb7  mov     rbx, r8
0x180002cba  mov     rdi, rdx
0x180002cbd  mov     dword ptr [rbp+arg_0], 0
0x180002cc4  mov     [rbp+arg_8], 0
0x180002ccb  mov     [rbp+pbstr], 0
0x180002cd3  mov     [rbp+bstrString], 0
0x180002cdb  mov     rax, [rdx]
0x180002cde  mov     rcx, [rax+10h]
0x180002ce2  mov     rax, [rcx]
0x180002ce5  lea     rdx, [rbp+arg_0]
0x180002ce9  mov     rax, [rax+0C0h]
0x180002cf0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002cf5  mov     rax, [rbx]
0x180002cf8  mov     rcx, [rax+10h]
0x180002cfc  mov     rax, [rcx]
0x180002cff  lea     rdx, [rbp+arg_8]
0x180002d03  mov     rax, [rax+0C0h]
0x180002d0a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002d0f  mov     eax, [rbp+arg_8]
0x180002d12  cmp     dword ptr [rbp+arg_0], eax
0x180002d15  jz      short loc_180002D1C
0x180002d17  setb    bl
0x180002d1a  jmp     short loc_180002D85
0x180002d1c  mov     rax, [rdi]
0x180002d1f  mov     rcx, [rax+10h]
0x180002d23  mov     rax, [rcx]
0x180002d26  lea     rdx, [rbp+pbstr]
0x180002d2a  mov     rax, [rax+68h]
0x180002d2e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002d33  mov     rax, [rbx]
0x180002d36  mov     rcx, [rax+10h]
0x180002d3a  mov     rax, [rcx]
0x180002d3d  lea     rdx, [rbp+bstrString]
0x180002d41  mov     rax, [rax+68h]
0x180002d45  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002d4a  mov     rcx, [rbp+pbstr]; pbstr
0x180002d4e  call    cs:__imp_SysStringLen
0x180002d54  mov     ebx, eax
0x180002d56  mov     rcx, [rbp+bstrString]; pbstr
0x180002d5a  call    cs:__imp_SysStringLen
0x180002d60  cmp     ebx, eax
0x180002d62  jnb     short loc_180002D68
0x180002d64  mov     bl, 1
0x180002d66  jmp     short loc_180002D85
0x180002d68  ja      short loc_180002D6E
0x180002d6a  test    ebx, ebx
0x180002d6c  jnz     short loc_180002D72
0x180002d6e  xor     bl, bl
0x180002d70  jmp     short loc_180002D85
0x180002d72  mov     rdx, [rbp+bstrString]
0x180002d76  mov     rcx, [rbp+pbstr]
0x180002d7a  call    cs:__imp__o__wcsicmp
0x180002d80  test    eax, eax
0x180002d82  sets    bl
0x180002d85  mov     rcx, [rbp+bstrString]; bstrString
0x180002d89  call    cs:__imp_SysFreeString
0x180002d8f  nop
0x180002d90  mov     rcx, [rbp+pbstr]; bstrString
0x180002d94  call    cs:__imp_SysFreeString
0x180002d9a  mov     al, bl
0x180002d9c  add     rsp, 20h
0x180002da0  pop     rdi
0x180002da1  pop     rbx
0x180002da2  pop     rbp
0x180002da3  retn
```
