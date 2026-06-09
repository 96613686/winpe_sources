# PiRegStateOpenClassKey

- ea: `0x140017e48`
- end: `0x140017fd3`
- name: `PiRegStateOpenClassKey`
- size: `395`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x1400181c4`
- `0x140018330`

## callees

- `0x14000a680`
- `0x140017e48`
- `0x1400185ac`
- `0x140018680`

## import_xrefs

- `ntoskrnl!_snwprintf` at `0x140017f29`
- `ntoskrnl!_snwprintf` at `0x140017f29`
- `ntoskrnl!ZwClose` at `0x140017f89`
- `ntoskrnl!ZwClose` at `0x140017f89`

## string_xrefs

- `0x140017ea2`: `\Registry\Machine\System\CurrentControlSet\Control\Class`

## pseudocode

```c
NTSTATUS __fastcall PiRegStateOpenClassKey(unsigned int *a1, __int64 a2, int a3, ULONG *a4, _QWORD *a5)
{
  NTSTATUS result; // eax
  __int64 v9; // r8
  ULONG v10; // r9d
  HANDLE v11; // rbx
  NTSTATUS v12; // eax
  ULONG v13; // esi
  int v14; // edi
  ULONG v15; // [rsp+70h] [rbp-61h] BYREF
  HANDLE Handle; // [rsp+78h] [rbp-59h] BYREF
  void *v17[2]; // [rsp+80h] [rbp-51h] BYREF
  wchar_t Dest[40]; // [rsp+90h] [rbp-41h] BYREF

  Handle = 0;
  v17[0] = 0;
  v15 = 0;
  *a5 = 0;
  if ( a4 )
    *a4 = 0;
  result = CmRegUtilOpenExistingWstrKey(
             0,
             L"\\Registry\\Machine\\System\\CurrentControlSet\\Control\\Class",
             131097,
             &Handle);
  if ( result >= 0 )
  {
    _snwprintf(
      Dest,
      0x27u,
      L"{%08X-%04X-%04X-%02X%02X-%02X%02X%02X%02X%02X%02X}",
      *a1,
      *((unsigned __int16 *)a1 + 2),
      *((unsigned __int16 *)a1 + 3),
      *((unsigned __int8 *)a1 + 8),
      *((unsigned __int8 *)a1 + 9),
      *((unsigned __int8 *)a1 + 10),
      *((unsigned __int8 *)a1 + 11),
      *((unsigned __int8 *)a1 + 12),
      *((unsigned __int8 *)a1 + 13),
      *((unsigned __int8 *)a1 + 14),
      *((unsigned __int8 *)a1 + 15));
    v11 = Handle;
    Dest[38] = 0;
    if ( a3 )
    {
      v12 = CmRegUtilCreateWstrKey((__int64)Handle, Dest, v9, v10, 0, &v15, v17);
      v13 = v15;
    }
    else
    {
      v12 = CmRegUtilOpenExistingWstrKey((__int64)Handle, Dest, 983103, v17);
      v13 = 2;
    }
    v14 = v12;
    ZwClose(v11);
    if ( v14 >= 0 )
    {
      *a5 = v17[0];
      if ( a4 )
        *a4 = v13;
    }
    return v14;
  }
  return result;
}

```

## disassembly

```asm
0x140017e48  mov     [rsp-8+arg_8], rbx
0x140017e4d  push    rbp
0x140017e4e  push    rsi
0x140017e4f  push    rdi
0x140017e50  push    r12
0x140017e52  push    r13
0x140017e54  push    r14
0x140017e56  push    r15
0x140017e58  lea     rbp, [rsp-1Fh]
0x140017e5d  sub     rsp, 0F0h
0x140017e64  mov     rax, cs:__security_cookie
0x140017e6b  xor     rax, rsp
0x140017e6e  mov     [rbp+4Fh+var_40], rax
0x140017e72  mov     r12, [rbp+4Fh+arg_20]
0x140017e76  xor     ebx, ebx
0x140017e78  mov     [rbp+4Fh+Handle], rbx
0x140017e7c  mov     r14, r9
0x140017e7f  mov     [rbp+4Fh+var_A0], rbx
0x140017e83  mov     r13d, r8d
0x140017e86  mov     [rbp+4Fh+var_B0], ebx
0x140017e89  mov     r15, rcx
0x140017e8c  mov     [r12], rbx
0x140017e90  test    r9, r9
0x140017e93  jz      short loc_140017E98
0x140017e95  mov     [r9], ebx
0x140017e98  lea     r9, [rbp+4Fh+Handle]
0x140017e9c  mov     r8d, 20019h
0x140017ea2  lea     rdx, aRegistryMachin; "\\Registry\\Machine\\System\\CurrentCon"...
0x140017ea9  xor     ecx, ecx
0x140017eab  call    CmRegUtilOpenExistingWstrKey
0x140017eb0  test    eax, eax
0x140017eb2  js      loc_140017FAB
0x140017eb8  movzx   ecx, byte ptr [r15+0Eh]
0x140017ebd  movzx   edx, byte ptr [r15+0Dh]
0x140017ec2  movzx   r8d, byte ptr [r15+0Ch]
0x140017ec7  movzx   r9d, byte ptr [r15+0Bh]
0x140017ecc  movzx   eax, byte ptr [r15+0Fh]
0x140017ed1  movzx   r10d, byte ptr [r15+0Ah]
0x140017ed6  movzx   r11d, byte ptr [r15+9]
0x140017edb  movzx   ebx, byte ptr [r15+8]
0x140017ee0  movzx   edi, word ptr [r15+6]
0x140017ee5  movzx   esi, word ptr [r15+4]
0x140017eea  mov     [rsp+120h+var_B8], eax
0x140017eee  mov     [rsp+120h+var_C0], ecx
0x140017ef2  lea     rcx, [rbp+4Fh+Dest]; Dest
0x140017ef6  mov     [rsp+120h+var_C8], edx
0x140017efa  mov     edx, 27h ; '''; Count
0x140017eff  mov     [rsp+120h+var_D0], r8d
0x140017f04  lea     r8, a08x04x04x02x02; "{%08X-%04X-%04X-%02X%02X-%02X%02X%02X%0"...
0x140017f0b  mov     [rsp+120h+var_D8], r9d
0x140017f10  mov     r9d, [r15]
0x140017f13  mov     [rsp+120h+var_E0], r10d
0x140017f18  mov     [rsp+120h+var_E8], r11d
0x140017f1d  mov     dword ptr [rsp+120h+var_F0], ebx
0x140017f21  mov     dword ptr [rsp+120h+var_F8], edi
0x140017f25  mov     dword ptr [rsp+120h+var_100], esi
0x140017f29  call    cs:__imp__snwprintf
0x140017f30  nop     dword ptr [rax+rax+00h]
0x140017f35  mov     rbx, [rbp+4Fh+Handle]
0x140017f39  lea     rdx, [rbp+4Fh+Dest]
0x140017f3d  xor     eax, eax
0x140017f3f  mov     rcx, rbx
0x140017f42  mov     [rbp+4Fh+var_44], ax
0x140017f46  test    r13d, r13d
0x140017f49  jz      short loc_140017F70
0x140017f4b  lea     rax, [rbp+4Fh+var_A0]
0x140017f4f  mov     [rsp+120h+var_F0], rax
0x140017f54  lea     rax, [rbp+4Fh+var_B0]
0x140017f58  mov     [rsp+120h+var_F8], rax
0x140017f5d  mov     [rsp+120h+var_100], 0
0x140017f66  call    CmRegUtilCreateWstrKey
0x140017f6b  mov     esi, [rbp+4Fh+var_B0]
0x140017f6e  jmp     short loc_140017F84
0x140017f70  lea     r9, [rbp+4Fh+var_A0]
0x140017f74  mov     r8d, 0F003Fh
0x140017f7a  call    CmRegUtilOpenExistingWstrKey
0x140017f7f  mov     esi, 2
0x140017f84  mov     rcx, rbx; Handle
0x140017f87  mov     edi, eax
0x140017f89  call    cs:__imp_ZwClose
0x140017f90  nop     dword ptr [rax+rax+00h]
0x140017f95  test    edi, edi
0x140017f97  js      short loc_140017FA9
0x140017f99  mov     rax, [rbp+4Fh+var_A0]
0x140017f9d  mov     [r12], rax
0x140017fa1  test    r14, r14
0x140017fa4  jz      short loc_140017FA9
0x140017fa6  mov     [r14], esi
0x140017fa9  mov     eax, edi
0x140017fab  mov     rcx, [rbp+4Fh+var_40]
0x140017faf  xor     rcx, rsp; StackCookie
0x140017fb2  call    __security_check_cookie
0x140017fb7  mov     rbx, [rsp+120h+arg_8]
0x140017fbf  add     rsp, 0F0h
0x140017fc6  pop     r15
0x140017fc8  pop     r14
0x140017fca  pop     r13
0x140017fcc  pop     r12
0x140017fce  pop     rdi
0x140017fcf  pop     rsi
0x140017fd0  pop     rbp
0x140017fd1  retn
```
