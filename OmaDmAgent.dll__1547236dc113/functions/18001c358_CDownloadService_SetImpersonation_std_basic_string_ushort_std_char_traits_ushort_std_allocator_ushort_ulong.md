# CDownloadService::SetImpersonation(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,ulong)

- ea: `0x18001c358`
- end: `0x18001c3f6`
- name: `?SetImpersonation@CDownloadService@@QEAAJV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@K@Z`
- size: `158`
- prototype: ``
- caller_count: `3`
- callee_count: `5`
- tags: `service_task`

## callers

- `0x180013330`
- `0x180013ce4`
- `0x180014680`

## callees

- `0x1800062ac`
- `0x1800070e4`
- `0x18000a290`
- `0x18001c358`
- `0x18001f420`

## pseudocode

```c
__int64 __fastcall CDownloadService::SetImpersonation(__int64 a1, __int64 a2, int a3)
{
  __int64 v4; // rbx
  unsigned int v6; // edi

  v4 = a2;
  v6 = 0;
  if ( *(_QWORD *)(a2 + 16) )
  {
    std::wstring::operator=(a1 + 16, a2);
    *(_DWORD *)(a1 + 48) = a3;
    *(_BYTE *)(a1 + 8) = 1;
  }
  else
  {
    if ( WPP_GLOBAL_Control != (LPCWSTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 4) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, WPP_26f90604ebd834e0d5ed309148d8b5dc_Traceguids);
    v6 = -2147024809;
  }
  LOBYTE(a2) = 1;
  std::wstring::_Tidy(v4, a2, 0);
  return v6;
}

```

## disassembly

```asm
0x18001c358  mov     [rsp+arg_10], rbx
0x18001c35d  push    rbp
0x18001c35e  push    rsi
0x18001c35f  push    rdi
0x18001c360  sub     rsp, 30h
0x18001c364  mov     rax, cs:__security_cookie
0x18001c36b  xor     rax, rsp
0x18001c36e  mov     [rsp+48h+var_20], rax
0x18001c373  mov     ebp, r8d
0x18001c376  mov     rbx, rdx
0x18001c379  mov     rsi, rcx
0x18001c37c  mov     [rsp+48h+var_28], rdx
0x18001c381  xor     edi, edi
0x18001c383  cmp     [rdx+10h], rdi
0x18001c387  jnz     short loc_18001C3BC
0x18001c389  lea     rax, WPP_GLOBAL_Control
0x18001c390  mov     rcx, cs:WPP_GLOBAL_Control
0x18001c397  cmp     rcx, rax
0x18001c39a  jz      short loc_18001C3B5
0x18001c39c  test    byte ptr [rcx+1Ch], 4
0x18001c3a0  jz      short loc_18001C3B5
0x18001c3a2  lea     edx, [rdi+0Ah]
0x18001c3a5  lea     r8, WPP_26f90604ebd834e0d5ed309148d8b5dc_Traceguids
0x18001c3ac  mov     rcx, [rcx+10h]
0x18001c3b0  call    WPP_SF_
0x18001c3b5  mov     edi, 80070057h
0x18001c3ba  jmp     short loc_18001C3CC
0x18001c3bc  add     rcx, 10h
0x18001c3c0  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x18001c3c5  mov     [rsi+30h], ebp
0x18001c3c8  mov     byte ptr [rsi+8], 1
0x18001c3cc  xor     r8d, r8d
0x18001c3cf  mov     dl, 1
0x18001c3d1  mov     rcx, rbx
0x18001c3d4  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x18001c3d9  mov     eax, edi
0x18001c3db  mov     rcx, [rsp+48h+var_20]
0x18001c3e0  xor     rcx, rsp; StackCookie
0x18001c3e3  call    __security_check_cookie
0x18001c3e8  mov     rbx, [rsp+48h+arg_10]
0x18001c3ed  add     rsp, 30h
0x18001c3f1  pop     rdi
0x18001c3f2  pop     rsi
0x18001c3f3  pop     rbp
0x18001c3f4  retn
```
