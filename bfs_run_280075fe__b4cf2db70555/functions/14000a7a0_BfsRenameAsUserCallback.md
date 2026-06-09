# BfsRenameAsUserCallback

- ea: `0x14000a7a0`
- end: `0x14000a90c`
- name: `BfsRenameAsUserCallback`
- size: `364`
- prototype: ``
- caller_count: `0`
- callee_count: `7`
- tags: `authz_impersonation`

## callees

- `0x140001008`
- `0x140006af4`
- `0x14000a7a0`
- `0x14000fc24`
- `0x14000fecc`
- `0x140012478`
- `0x140013730`

## import_xrefs

- `FLTMGR!FltSetInformationFile` at `0x14000a83f`
- `FLTMGR!FltSetInformationFile` at `0x14000a83f`

## pseudocode

```c
__int64 __fastcall BfsRenameAsUserCallback(__int64 a1, struct _FLT_INSTANCE *a2, __int64 a3, __int64 a4)
{
  void *v4; // rcx
  int v8; // eax
  __int64 v9; // r8
  __int64 v10; // r9
  unsigned int v11; // edi
  NTSTATUS v12; // eax
  __int64 v13; // rcx
  __int64 v14; // r8
  __int64 v15; // r9
  __int64 v16; // rax
  __int64 v17; // r14
  __int64 v18; // rbx
  struct _RTL_BITMAP *FileName; // rax
  __int64 v20; // rdx
  FILE_INFORMATION_CLASS FileInformationClass; // [rsp+20h] [rbp-59h]
  FILE_INFORMATION_CLASS FileInformationClassa; // [rsp+20h] [rbp-59h]
  NTSTATUS v24; // [rsp+30h] [rbp-49h] BYREF
  struct _RTL_BITMAP v25; // [rsp+38h] [rbp-41h] BYREF
  struct _RTL_BITMAP v26; // [rsp+48h] [rbp-31h] BYREF
  __int128 v27; // [rsp+58h] [rbp-21h] BYREF
  __int64 v28; // [rsp+68h] [rbp-11h]
  struct _EVENT_DATA_DESCRIPTOR v29; // [rsp+70h] [rbp-9h] BYREF
  NTSTATUS *v30; // [rsp+90h] [rbp+17h]
  __int64 v31; // [rsp+98h] [rbp+1Fh]

  v4 = *(void **)a4;
  v27 = 0;
  v28 = 0;
  v8 = BfsImpersonateUser(v4, (__int64)&v27);
  v11 = v8;
  if ( v8 >= 0 )
  {
    v12 = FltSetInformationFile(
            a2,
            *(PFILE_OBJECT *)(*(_QWORD *)(a3 + 16) + 8LL),
            *(PVOID *)(*(_QWORD *)(a3 + 16) + 56LL),
            *(_DWORD *)(*(_QWORD *)(a3 + 16) + 24LL),
            *(FILE_INFORMATION_CLASS *)(*(_QWORD *)(a3 + 16) + 32LL));
    *(_DWORD *)(a4 + 32) = v12;
    v11 = v12;
    if ( v12 >= 0 )
    {
      v16 = *(_QWORD *)(a4 + 24);
      if ( v16 )
      {
        v17 = *(_QWORD *)(v16 + 48);
        if ( v17 )
        {
          if ( !*(_BYTE *)(a4 + 36) )
          {
            v18 = *(_QWORD *)(a4 + 8);
            FileName = (struct _RTL_BITMAP *)BfsGetFileName(&v26, v18);
            v20 = *(_QWORD *)(a4 + 16);
            v26 = *FileName;
            v25 = *(struct _RTL_BITMAP *)BfsGetFileName(&v25, v20);
            BfsRenameEntry(v17, v18 + 24, &v26, &v25);
          }
        }
      }
    }
    else if ( (unsigned int)dword_140019000 > 3 )
    {
      v24 = v12;
      v30 = &v24;
      v31 = 4;
      tlgWriteTransfer_EtwWriteTransfer(v13, (unsigned __int8 *)&byte_140016D91, v14, v15, FileInformationClassa, &v29);
    }
    BfsRevertTokenImpersonation((__int64)&v27);
  }
  else if ( (unsigned int)dword_140019000 > 3 )
  {
    v24 = v8;
    v31 = 4;
    v30 = &v24;
    tlgWriteTransfer_EtwWriteTransfer(
      (unsigned int)dword_140019000,
      (unsigned __int8 *)&byte_140016D91,
      v9,
      v10,
      FileInformationClass,
      &v29);
  }
  return v11;
}

```

## disassembly

```asm
0x14000a7a0  push    rbp
0x14000a7a2  push    rbx
0x14000a7a3  push    rsi
0x14000a7a4  push    rdi
0x14000a7a5  push    r14
0x14000a7a7  lea     rbp, [rsp-37h]
0x14000a7ac  sub     rsp, 0B0h
0x14000a7b3  mov     rax, cs:__security_cookie
0x14000a7ba  xor     rax, rsp
0x14000a7bd  mov     [rbp+57h+var_30], rax
0x14000a7c1  mov     rcx, [r9]
0x14000a7c4  mov     rbx, rdx
0x14000a7c7  xorps   xmm0, xmm0
0x14000a7ca  lea     rdx, [rbp+57h+var_78]
0x14000a7ce  xor     eax, eax
0x14000a7d0  mov     rsi, r9
0x14000a7d3  movups  [rbp+57h+var_78], xmm0
0x14000a7d7  mov     [rbp+57h+var_68], rax
0x14000a7db  mov     r14, r8
0x14000a7de  call    BfsImpersonateUser
0x14000a7e3  mov     edi, eax
0x14000a7e5  test    eax, eax
0x14000a7e7  jns     short loc_14000A825
0x14000a7e9  mov     ecx, cs:dword_140019000; int
0x14000a7ef  cmp     ecx, 3
0x14000a7f2  jbe     loc_14000A8EF
0x14000a7f8  mov     [rbp+57h+var_A0], eax
0x14000a7fb  lea     rdx, byte_140016D91; int
0x14000a802  lea     rax, [rbp+57h+var_A0]
0x14000a806  mov     [rbp+57h+var_38], 4
0x14000a80e  mov     [rbp+57h+var_40], rax
0x14000a812  lea     rax, [rbp+57h+var_60]
0x14000a816  mov     [rsp+0D0h+var_A8], rax; PEVENT_DATA_DESCRIPTOR
0x14000a81b  call    _tlgWriteTransfer_EtwWriteTransfer
0x14000a820  jmp     loc_14000A8EF
0x14000a825  mov     rdx, [r14+10h]
0x14000a829  mov     rcx, rbx; Instance
0x14000a82c  mov     eax, [rdx+20h]
0x14000a82f  mov     r9d, [rdx+18h]; Length
0x14000a833  mov     r8, [rdx+38h]; FileInformation
0x14000a837  mov     rdx, [rdx+8]; FileObject
0x14000a83b  mov     [rsp+0D0h+FileInformationClass], eax; int
0x14000a83f  call    cs:__imp_FltSetInformationFile
0x14000a846  nop     dword ptr [rax+rax+00h]
0x14000a84b  mov     [rsi+20h], eax
0x14000a84e  mov     edi, eax
0x14000a850  test    eax, eax
0x14000a852  jns     short loc_14000A88D
0x14000a854  mov     eax, cs:dword_140019000
0x14000a85a  cmp     eax, 3
0x14000a85d  jbe     loc_14000A8E6
0x14000a863  lea     rax, [rbp+57h+var_A0]
0x14000a867  mov     [rbp+57h+var_A0], edi
0x14000a86a  mov     [rbp+57h+var_40], rax
0x14000a86e  lea     rdx, byte_140016D91; int
0x14000a875  lea     rax, [rbp+57h+var_60]
0x14000a879  mov     [rbp+57h+var_38], 4
0x14000a881  mov     [rsp+0D0h+var_A8], rax; PEVENT_DATA_DESCRIPTOR
0x14000a886  call    _tlgWriteTransfer_EtwWriteTransfer
0x14000a88b  jmp     short loc_14000A8E6
0x14000a88d  mov     rax, [rsi+18h]
0x14000a891  test    rax, rax
0x14000a894  jz      short loc_14000A8E6
0x14000a896  mov     r14, [rax+30h]
0x14000a89a  test    r14, r14
0x14000a89d  jz      short loc_14000A8E6
0x14000a89f  cmp     byte ptr [rsi+24h], 0
0x14000a8a3  jnz     short loc_14000A8E6
0x14000a8a5  mov     rbx, [rsi+8]
0x14000a8a9  lea     rcx, [rbp+57h+var_88]
0x14000a8ad  mov     rdx, rbx
0x14000a8b0  call    BfsGetFileName
0x14000a8b5  mov     rdx, [rsi+10h]
0x14000a8b9  lea     rcx, [rbp+57h+var_98]
0x14000a8bd  movups  xmm1, xmmword ptr [rax]
0x14000a8c0  movdqu  [rbp+57h+var_88], xmm1
0x14000a8c5  call    BfsGetFileName
0x14000a8ca  lea     rdx, [rbx+18h]
0x14000a8ce  mov     rcx, r14
0x14000a8d1  lea     r9, [rbp+57h+var_98]
0x14000a8d5  lea     r8, [rbp+57h+var_88]
0x14000a8d9  movups  xmm1, xmmword ptr [rax]
0x14000a8dc  movdqu  [rbp+57h+var_98], xmm1
0x14000a8e1  call    BfsRenameEntry
0x14000a8e6  lea     rcx, [rbp+57h+var_78]
0x14000a8ea  call    BfsRevertTokenImpersonation
0x14000a8ef  mov     eax, edi
0x14000a8f1  mov     rcx, [rbp+57h+var_30]
0x14000a8f5  xor     rcx, rsp; StackCookie
0x14000a8f8  call    __security_check_cookie
0x14000a8fd  add     rsp, 0B0h
0x14000a904  pop     r14
0x14000a906  pop     rdi
0x14000a907  pop     rsi
0x14000a908  pop     rbx
0x14000a909  pop     rbp
0x14000a90a  retn
```
