# ManualInterfaceRegistration::CreateInstance(ushort const *,std::unique_ptr<DiagHubCommon::ComProxyRegistration,std::default_delete<DiagHubCommon::ComProxyRegistration>> &)

- ea: `0x14000edcc`
- end: `0x14000eedf`
- name: `?CreateInstance@ManualInterfaceRegistration@@SAJPEBGAEAV?$unique_ptr@VComProxyRegistration@DiagHubCommon@@U?$default_delete@VComProxyRegistration@DiagHubCommon@@@std@@@std@@@Z`
- size: `275`
- prototype: `__int64 __fastcall(unsigned __int16 *, ManualInterfaceRegistration **)`
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x14000f098`

## callees

- `0x14000edcc`
- `0x14000eee0`
- `0x140013834`
- `0x14001473e`
- `0x140014c70`

## pseudocode

```c
// Hidden C++ exception states: #wind=11
__int64 __fastcall ManualInterfaceRegistration::CreateInstance(unsigned __int16 *a1, ManualInterfaceRegistration **a2)
{
  ManualInterfaceRegistration *v4; // r8
  int v5; // eax
  int v6; // eax
  ManualInterfaceRegistration *v7; // rcx
  __int64 result; // rax
  unsigned int v9; // ebx
  ManualInterfaceRegistration *v10; // [rsp+20h] [rbp-18h]
  void *v11; // [rsp+28h] [rbp-10h]

  try
  {
    v11 = operator new(0x248u);
    memset_0(v11, 0, 0x248u);
    v4 = ManualInterfaceRegistration::ManualInterfaceRegistration((ManualInterfaceRegistration *)v11, a1);
    v10 = v4;
    v5 = *((_DWORD *)v4 + 136);
    if ( v5 || !*((_QWORD *)v4 + 67) )
    {
      v9 = (unsigned __int16)v5 | 0x80070000;
      if ( v5 <= 0 )
        v9 = *((_DWORD *)v4 + 136);
      if ( !v4 )
        return v9;
    }
    else
    {
      v6 = *((_DWORD *)v4 + 142);
      if ( !v6 && *((_QWORD *)v4 + 70) )
      {
        v7 = *a2;
        *a2 = v4;
        if ( v7 )
          (**(void (__fastcall ***)(ManualInterfaceRegistration *, __int64))v7)(v7, 1);
        return 0;
      }
      v9 = (unsigned __int16)v6 | 0x80070000;
      if ( v6 <= 0 )
        v9 = *((_DWORD *)v4 + 142);
      if ( !v4 )
        return v9;
    }
    (**(void (__fastcall ***)(ManualInterfaceRegistration *, __int64))v4)(v4, 1);
    return v9;
  }
  catch ( std::bad_alloc )
  {
    if ( v10 )
      (**(void (__fastcall ***)(ManualInterfaceRegistration *, __int64))v10)(v10, 1);
    return 2147942414LL;
  }
  v11 = operator new(0x248u);
}

```

## disassembly

```asm
0x14000edcc  mov     [rsp+arg_10], rbx
0x14000edd1  mov     [rsp+arg_18], rsi
0x14000edd6  push    rdi
0x14000edd7  sub     rsp, 30h
0x14000eddb  mov     rbx, rdx
0x14000edde  mov     rsi, rcx
0x14000ede1  mov     [rsp+38h+var_18], 0
0x14000edea  mov     ecx, 248h; Size
0x14000edef  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x14000edf4  mov     rdi, rax
0x14000edf7  mov     [rsp+38h+var_10], rax
0x14000edfc  xor     edx, edx; Val
0x14000edfe  mov     r8d, 248h; Size
0x14000ee04  mov     rcx, rax; void *
0x14000ee07  call    memset_0
0x14000ee0c  mov     rdx, rsi; unsigned __int16 *
0x14000ee0f  mov     rcx, rdi; this
0x14000ee12  call    ??0ManualInterfaceRegistration@@QEAA@PEBG@Z; ManualInterfaceRegistration::ManualInterfaceRegistration(ushort const *)
0x14000ee17  mov     r8, rax
0x14000ee1a  mov     [rsp+38h+var_18], rax
0x14000ee1f  mov     eax, [rax+220h]
0x14000ee25  test    eax, eax
0x14000ee27  jnz     short loc_14000EE84
0x14000ee29  cmp     qword ptr [r8+218h], 0
0x14000ee31  jz      short loc_14000EE84
0x14000ee33  mov     eax, [r8+238h]
0x14000ee3a  test    eax, eax
0x14000ee3c  jnz     short loc_14000EE69
0x14000ee3e  cmp     qword ptr [r8+230h], 0
0x14000ee46  jz      short loc_14000EE69
0x14000ee48  mov     rcx, [rbx]
0x14000ee4b  mov     [rbx], r8
0x14000ee4e  test    rcx, rcx
0x14000ee51  jz      short loc_14000EE65
0x14000ee53  mov     rax, [rcx]
0x14000ee56  mov     edx, 1
0x14000ee5b  mov     rax, [rax]
0x14000ee5e  call    cs:__guard_dispatch_icall_fptr
0x14000ee64  nop
0x14000ee65  xor     eax, eax
0x14000ee67  jmp     short loc_14000EECF
0x14000ee69  movzx   ebx, ax
0x14000ee6c  or      ebx, 80070000h
0x14000ee72  test    eax, eax
0x14000ee74  cmovle  ebx, eax
0x14000ee77  test    r8, r8
0x14000ee7a  jz      short loc_14000EEAB
0x14000ee7c  mov     rdx, [r8]
0x14000ee7f  mov     rax, [rdx]
0x14000ee82  jmp     short loc_14000EE9D
0x14000ee84  movzx   ebx, ax
0x14000ee87  or      ebx, 80070000h
0x14000ee8d  test    eax, eax
0x14000ee8f  cmovle  ebx, eax
0x14000ee92  test    r8, r8
0x14000ee95  jz      short loc_14000EEAB
0x14000ee97  mov     rcx, [r8]
0x14000ee9a  mov     rax, [rcx]
0x14000ee9d  mov     edx, 1
0x14000eea2  mov     rcx, r8
0x14000eea5  call    cs:__guard_dispatch_icall_fptr
0x14000eeab  mov     eax, ebx
0x14000eead  jmp     short loc_14000EECF
0x14000eeaf  mov     rcx, [rsp+38h+var_18]
0x14000eeb4  test    rcx, rcx
0x14000eeb7  jz      short loc_14000EECA
0x14000eeb9  mov     rax, [rcx]
0x14000eebc  mov     edx, 1
0x14000eec1  mov     rax, [rax]
0x14000eec4  call    cs:__guard_dispatch_icall_fptr
0x14000eeca  mov     eax, 8007000Eh
0x14000eecf  mov     rbx, [rsp+38h+arg_10]
0x14000eed4  mov     rsi, [rsp+38h+arg_18]
0x14000eed9  add     rsp, 30h
0x14000eedd  pop     rdi
0x14000eede  retn
```
