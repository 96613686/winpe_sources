# SetVariableImpl

- ea: `0x1400ab780`
- end: `0x1400ab8f4`
- name: `SetVariableImpl`
- size: `372`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `authz_impersonation, loader_planting`

## callees

- `0x140050288`
- `0x1400830cc`
- `0x1400a3230`
- `0x1400aac70`
- `0x1400ab780`

## import_xrefs

- `ntdll!RtlAdjustPrivilege` at `0x1400ab7b4`
- `ntdll!RtlAdjustPrivilege` at `0x1400ab8b1`
- `ntdll!RtlAdjustPrivilege` at `0x1400ab7b4`
- `ntdll!RtlAdjustPrivilege` at `0x1400ab8b1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400ab864`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400ab864`
- `api-ms-win-core-firmware-l1-1-0!SetFirmwareEnvironmentVariableExW` at `0x1400ab83f`
- `api-ms-win-core-firmware-l1-1-0!SetFirmwareEnvironmentVariableExW` at `0x1400ab83f`

## pseudocode

```c
__int64 __fastcall SetVariableImpl(__int64 a1, __int64 a2, __int64 a3, __int64 a4, unsigned int a5, int a6)
{
  NTSTATUS v9; // eax
  unsigned int v10; // ebx
  int v11; // eax
  const char *v12; // r9
  signed int LastError; // eax
  NTSTATUS v14; // eax
  NTSTATUS v15; // edi
  int v17; // [rsp+20h] [rbp-40h]
  unsigned __int8 OldValue[8]; // [rsp+30h] [rbp-30h] BYREF
  _QWORD v19[2]; // [rsp+38h] [rbp-28h] BYREF
  _WORD v20[12]; // [rsp+48h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+28h]

  OldValue[0] = 0;
  v9 = RtlAdjustPrivilege(0x16u, 1u, NtCurrentTeb()->IsImpersonating != 0, OldValue);
  v10 = v9;
  if ( v9 >= 0 )
  {
    v19[0] = v20;
    v19[1] = v20;
    v20[0] = 0;
    v11 = GUIDToWstring(a2, v19);
    v10 = v11;
    if ( v11 >= 0 )
    {
      v10 = 0;
      if ( !(unsigned int)SetFirmwareEnvironmentVariableExW(a3, v19[0], a4, a5) )
      {
        wil::details::in1diag3::Log_GetLastError(
          retaddr,
          (void *)0x758,
          (unsigned int)"minkernel\\fs\\minstore\\msthunks.cpp",
          v12);
        LastError = GetLastError();
        v10 = LastError;
        if ( LastError == 1168 || LastError == 203 )
        {
          v10 = -1073741275;
        }
        else if ( LastError > 0 )
        {
          v10 = (unsigned __int16)LastError | 0xC0070000;
        }
      }
      if ( !OldValue[0] )
      {
        v14 = RtlAdjustPrivilege(0x16u, 0, NtCurrentTeb()->IsImpersonating != 0, OldValue);
        v15 = v14;
        if ( v14 < 0 )
        {
          wil::details::in1diag3::Return_NtStatus(
            retaddr,
            (void *)0x768,
            (unsigned int)"minkernel\\fs\\minstore\\msthunks.cpp",
            (const char *)(unsigned int)v14,
            a6);
          v10 = v15;
        }
      }
    }
    else
    {
      wil::details::in1diag3::Return_NtStatus(
        retaddr,
        (void *)0x74F,
        (unsigned int)"minkernel\\fs\\minstore\\msthunks.cpp",
        (const char *)(unsigned int)v11,
        v17);
    }
    utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::_Uninit(v19);
  }
  else
  {
    wil::details::in1diag3::Return_NtStatus(
      retaddr,
      (void *)0x74C,
      (unsigned int)"minkernel\\fs\\minstore\\msthunks.cpp",
      (const char *)(unsigned int)v9,
      v17);
  }
  return v10;
}

```

## disassembly

```asm
0x1400ab780  push    rbp
0x1400ab782  push    rbx
0x1400ab783  push    rsi
0x1400ab784  push    rdi
0x1400ab785  push    r14
0x1400ab787  mov     rbp, rsp
0x1400ab78a  sub     rsp, 60h
0x1400ab78e  mov     [rbp+OldValue], 0
0x1400ab792  mov     rsi, r9
0x1400ab795  mov     eax, gs:179Ch
0x1400ab79d  lea     r9, [rbp+OldValue]; OldValue
0x1400ab7a1  test    eax, eax
0x1400ab7a3  mov     r14, r8
0x1400ab7a6  mov     rdi, rdx
0x1400ab7a9  mov     ecx, 16h; Privilege
0x1400ab7ae  setnz   r8b; ForThread
0x1400ab7b2  mov     dl, 1; NewValue
0x1400ab7b4  call    cs:__imp_RtlAdjustPrivilege
0x1400ab7bb  nop     dword ptr [rax+rax+00h]
0x1400ab7c0  mov     ebx, eax
0x1400ab7c2  test    eax, eax
0x1400ab7c4  jns     short loc_1400AB7E3
0x1400ab7c6  mov     rcx, [rbp+28h]; this
0x1400ab7ca  lea     r8, aMinkernelFsMin_18; "minkernel\\fs\\minstore\\msthunks.cpp"
0x1400ab7d1  mov     r9d, eax; char *
0x1400ab7d4  mov     edx, 74Ch; void *
0x1400ab7d9  call    ?Return_NtStatus@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Return_NtStatus(void *,uint,char const *,long)
0x1400ab7de  jmp     loc_1400AB8E6
0x1400ab7e3  lea     rax, [rbp+var_18]
0x1400ab7e7  mov     rcx, rdi
0x1400ab7ea  mov     [rbp+var_28], rax
0x1400ab7ee  lea     rdx, [rbp+var_28]
0x1400ab7f2  lea     rax, [rbp+var_18]
0x1400ab7f6  mov     [rbp+var_20], rax
0x1400ab7fa  xor     eax, eax
0x1400ab7fc  mov     [rbp+var_18], ax
0x1400ab800  call    ?GUIDToWstring@@YAJAEBU_GUID@@AEAV?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@@Z; GUIDToWstring(_GUID const &,utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>> &)
0x1400ab805  mov     ebx, eax
0x1400ab807  test    eax, eax
0x1400ab809  jns     short loc_1400AB828
0x1400ab80b  mov     rcx, [rbp+28h]; this
0x1400ab80f  lea     r8, aMinkernelFsMin_18; "minkernel\\fs\\minstore\\msthunks.cpp"
0x1400ab816  mov     r9d, eax; char *
0x1400ab819  mov     edx, 74Fh; void *
0x1400ab81e  call    ?Return_NtStatus@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Return_NtStatus(void *,uint,char const *,long)
0x1400ab823  jmp     loc_1400AB8DD
0x1400ab828  mov     eax, [rbp+arg_28]
0x1400ab82b  mov     r8, rsi
0x1400ab82e  mov     r9d, [rbp+arg_20]
0x1400ab832  mov     rcx, r14
0x1400ab835  mov     rdx, [rbp+var_28]
0x1400ab839  xor     ebx, ebx
0x1400ab83b  mov     [rsp+60h+var_40], eax; int
0x1400ab83f  call    cs:__imp_SetFirmwareEnvironmentVariableExW
0x1400ab846  nop     dword ptr [rax+rax+00h]
0x1400ab84b  test    eax, eax
0x1400ab84d  jnz     short loc_1400AB894
0x1400ab84f  mov     rcx, [rbp+28h]; this
0x1400ab853  lea     r8, aMinkernelFsMin_18; "minkernel\\fs\\minstore\\msthunks.cpp"
0x1400ab85a  mov     edx, 758h; void *
0x1400ab85f  call    ?Log_GetLastError@in1diag3@details@wil@@YAKPEAXIPEBD@Z; wil::details::in1diag3::Log_GetLastError(void *,uint,char const *)
0x1400ab864  call    cs:__imp_GetLastError
0x1400ab86b  nop     dword ptr [rax+rax+00h]
0x1400ab870  mov     ebx, eax
0x1400ab872  cmp     eax, 490h
0x1400ab877  jz      short loc_1400AB88F
0x1400ab879  cmp     eax, 0CBh
0x1400ab87e  jz      short loc_1400AB88F
0x1400ab880  test    eax, eax
0x1400ab882  jle     short loc_1400AB894
0x1400ab884  movzx   ebx, ax
0x1400ab887  or      ebx, 0C0070000h
0x1400ab88d  jmp     short loc_1400AB894
0x1400ab88f  mov     ebx, 0C0000225h
0x1400ab894  cmp     [rbp+OldValue], 0
0x1400ab898  jnz     short loc_1400AB8DD
0x1400ab89a  mov     eax, gs:179Ch
0x1400ab8a2  lea     r9, [rbp+OldValue]; OldValue
0x1400ab8a6  test    eax, eax
0x1400ab8a8  setnz   r8b; ForThread
0x1400ab8ac  xor     edx, edx; NewValue
0x1400ab8ae  lea     ecx, [rdx+16h]; Privilege
0x1400ab8b1  call    cs:__imp_RtlAdjustPrivilege
0x1400ab8b8  nop     dword ptr [rax+rax+00h]
0x1400ab8bd  mov     edi, eax
0x1400ab8bf  test    eax, eax
0x1400ab8c1  jns     short loc_1400AB8DD
0x1400ab8c3  mov     rcx, [rbp+28h]; this
0x1400ab8c7  lea     r8, aMinkernelFsMin_18; "minkernel\\fs\\minstore\\msthunks.cpp"
0x1400ab8ce  mov     r9d, eax; char *
0x1400ab8d1  mov     edx, 768h; void *
0x1400ab8d6  call    ?Return_NtStatus@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Return_NtStatus(void *,uint,char const *,long)
0x1400ab8db  mov     ebx, edi
0x1400ab8dd  lea     rcx, [rbp+var_28]
0x1400ab8e1  call    ?_Uninit@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@AEAAXXZ; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::_Uninit(void)
0x1400ab8e6  mov     eax, ebx
0x1400ab8e8  add     rsp, 60h
0x1400ab8ec  pop     r14
0x1400ab8ee  pop     rdi
0x1400ab8ef  pop     rsi
0x1400ab8f0  pop     rbx
0x1400ab8f1  pop     rbp
0x1400ab8f2  retn
```
