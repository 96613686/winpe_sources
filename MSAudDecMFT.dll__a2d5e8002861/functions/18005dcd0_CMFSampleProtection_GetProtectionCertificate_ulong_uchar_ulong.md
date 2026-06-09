# CMFSampleProtection::GetProtectionCertificate(ulong,uchar * *,ulong *)

- ea: `0x18005dcd0`
- end: `0x18005dd7b`
- name: `?GetProtectionCertificate@CMFSampleProtection@@UEAAJKPEAPEAEPEAK@Z`
- size: `171`
- prototype: `__int64 __fastcall(CMFSampleProtection *this, int, unsigned __int8 **, unsigned int *)`
- caller_count: `0`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callees

- `0x18005dcd0`
- `0x18009606c`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18005dd2a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18005dd2a`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CMFSampleProtection::GetProtectionCertificate(
        CMFSampleProtection *this,
        int a2,
        unsigned __int8 **a3,
        unsigned int *a4)
{
  const void *v6; // rsi
  unsigned int v7; // ebx
  unsigned __int8 *v8; // rax
  unsigned int v9; // edi

  if ( !a3 || !a4 )
    return 2147500035LL;
  if ( a2 == 3 )
  {
    v6 = (const void *)*((_QWORD *)this + 3);
    v7 = *((_DWORD *)this + 8);
  }
  else
  {
    if ( a2 != 4 )
      return 2147500033LL;
    v6 = (const void *)*((_QWORD *)this + 45);
    v7 = *((_DWORD *)this + 92);
  }
  *a3 = 0;
  *a4 = 0;
  if ( !v6 || !v7 )
    return 2147549183LL;
  v8 = (unsigned __int8 *)CoTaskMemAlloc(v7);
  *a3 = v8;
  if ( v8 )
  {
    v9 = 0;
    memcpy_0(v8, v6, v7);
    *a4 = v7;
  }
  else
  {
    return (unsigned int)-2147024882;
  }
  return v9;
}

```

## disassembly

```asm
0x18005dcd0  push    rbx
0x18005dcd2  push    rbp
0x18005dcd3  push    rsi
0x18005dcd4  push    rdi
0x18005dcd5  push    r14
0x18005dcd7  sub     rsp, 20h
0x18005dcdb  mov     r14, r9
0x18005dcde  mov     rdi, r8
0x18005dce1  test    r8, r8
0x18005dce4  jz      loc_18005DD6A
0x18005dcea  test    r9, r9
0x18005dced  jz      short loc_18005DD6A
0x18005dcef  cmp     edx, 3
0x18005dcf2  jnz     short loc_18005DCFD
0x18005dcf4  mov     rsi, [rcx+18h]
0x18005dcf8  mov     ebx, [rcx+20h]
0x18005dcfb  jmp     short loc_18005DD0F
0x18005dcfd  cmp     edx, 4
0x18005dd00  jnz     short loc_18005DD63
0x18005dd02  mov     rsi, [rcx+168h]
0x18005dd09  mov     ebx, [rcx+170h]
0x18005dd0f  mov     qword ptr [r8], 0
0x18005dd16  mov     dword ptr [r9], 0
0x18005dd1d  test    rsi, rsi
0x18005dd20  jz      short loc_18005DD5C
0x18005dd22  test    ebx, ebx
0x18005dd24  jz      short loc_18005DD5C
0x18005dd26  mov     ecx, ebx; cb
0x18005dd28  mov     ebp, ebx
0x18005dd2a  call    cs:__imp_CoTaskMemAlloc
0x18005dd31  nop     dword ptr [rax+rax+00h]
0x18005dd36  mov     [rdi], rax
0x18005dd39  test    rax, rax
0x18005dd3c  jnz     short loc_18005DD45
0x18005dd3e  mov     edi, 8007000Eh
0x18005dd43  jmp     short loc_18005DD58
0x18005dd45  xor     edi, edi
0x18005dd47  mov     r8, rbp; Size
0x18005dd4a  mov     rdx, rsi; Src
0x18005dd4d  mov     rcx, rax; void *
0x18005dd50  call    memcpy_0
0x18005dd55  mov     [r14], ebx
0x18005dd58  mov     eax, edi
0x18005dd5a  jmp     short loc_18005DD6F
0x18005dd5c  mov     eax, 8000FFFFh
0x18005dd61  jmp     short loc_18005DD6F
0x18005dd63  mov     eax, 80004001h
0x18005dd68  jmp     short loc_18005DD6F
0x18005dd6a  mov     eax, 80004003h
0x18005dd6f  add     rsp, 20h
0x18005dd73  pop     r14
0x18005dd75  pop     rdi
0x18005dd76  pop     rsi
0x18005dd77  pop     rbp
0x18005dd78  pop     rbx
0x18005dd79  retn
```
