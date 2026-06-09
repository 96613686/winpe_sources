# CActiveScriptEngine::GetHostInfo(hostinfo,void * *)

- ea: `0x180019a60`
- end: `0x180019aee`
- name: `?GetHostInfo@CActiveScriptEngine@@UEAAJW4hostinfo@@PEAPEAX@Z`
- size: `142`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `service_task`

## callees

- `0x180019a60`

## import_xrefs

- `ole32!CoTaskMemAlloc` at `0x180019a79`
- `ole32!CoTaskMemAlloc` at `0x180019aaa`
- `ole32!CoTaskMemAlloc` at `0x180019a79`
- `ole32!CoTaskMemAlloc` at `0x180019aaa`
- `KERNEL32!GetACP` at `0x180019ac6`
- `KERNEL32!GetACP` at `0x180019ac6`

## pseudocode

```c
__int64 __fastcall CActiveScriptEngine::GetHostInfo(__int64 a1, int a2, _QWORD *a3)
{
  _DWORD *v5; // rax
  LPVOID v7; // rax
  UINT ACP; // ecx

  if ( !a2 )
  {
    v5 = CoTaskMemAlloc(4u);
    *a3 = v5;
    if ( v5 )
    {
      *v5 = *(_DWORD *)(*(_QWORD *)(a1 + 32) + 168LL);
      return 0;
    }
    return 2147942414LL;
  }
  if ( a2 != 1 )
    return 2147500037LL;
  v7 = CoTaskMemAlloc(4u);
  *a3 = v7;
  if ( !v7 )
    return 2147942414LL;
  ACP = *(_DWORD *)(*(_QWORD *)(a1 + 32) + 164LL);
  if ( !ACP )
    ACP = GetACP();
  *(_DWORD *)*a3 = ACP;
  return 0;
}

```

## disassembly

```asm
0x180019a60  mov     [rsp+arg_0], rbx
0x180019a65  push    rdi
0x180019a66  sub     rsp, 20h
0x180019a6a  mov     rbx, r8
0x180019a6d  mov     rdi, rcx
0x180019a70  test    edx, edx
0x180019a72  jnz     short loc_180019AA0
0x180019a74  mov     ecx, 4; cb
0x180019a79  call    cs:__imp_CoTaskMemAlloc
0x180019a7f  mov     [rbx], rax
0x180019a82  test    rax, rax
0x180019a85  jz      short loc_180019AE0
0x180019a87  mov     rcx, [rdi+20h]
0x180019a8b  mov     edx, [rcx+0A8h]
0x180019a91  mov     [rax], edx
0x180019a93  xor     eax, eax
0x180019a95  mov     rbx, [rsp+28h+arg_0]
0x180019a9a  add     rsp, 20h
0x180019a9e  pop     rdi
0x180019a9f  retn
0x180019aa0  cmp     edx, 1
0x180019aa3  jnz     short loc_180019AE7
0x180019aa5  mov     ecx, 4; cb
0x180019aaa  call    cs:__imp_CoTaskMemAlloc
0x180019ab0  mov     [rbx], rax
0x180019ab3  test    rax, rax
0x180019ab6  jz      short loc_180019AE0
0x180019ab8  mov     rax, [rdi+20h]
0x180019abc  mov     ecx, [rax+0A4h]
0x180019ac2  test    ecx, ecx
0x180019ac4  jnz     short loc_180019ACE
0x180019ac6  call    cs:__imp_GetACP
0x180019acc  mov     ecx, eax
0x180019ace  mov     rax, [rbx]
0x180019ad1  mov     rbx, [rsp+28h+arg_0]
0x180019ad6  mov     [rax], ecx
0x180019ad8  xor     eax, eax
0x180019ada  add     rsp, 20h
0x180019ade  pop     rdi
0x180019adf  retn
0x180019ae0  mov     eax, 8007000Eh
0x180019ae5  jmp     short loc_180019A95
0x180019ae7  mov     eax, 80004005h
0x180019aec  jmp     short loc_180019A95
```
