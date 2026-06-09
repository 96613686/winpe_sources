# RsopReportInstallFailure

- ea: `0x180004d60`
- end: `0x180004e2a`
- name: `RsopReportInstallFailure`
- size: `202`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `installer_update`

## callees

- `0x1800016d0`
- `0x180004d60`
- `0x180008e8c`
- `0x18000a554`
- `0x1800131d4`

## pseudocode

```c
__int64 __fastcall RsopReportInstallFailure(__int64 *a1, const unsigned __int16 *a2, int a3)
{
  __int64 v3; // rsi
  struct CAppInfo *v6; // rbx
  struct _GUID v8; // [rsp+20h] [rbp-48h] BYREF
  struct _GUID v9; // [rsp+30h] [rbp-38h] BYREF

  v3 = *a1;
  v9 = 0;
  if ( v3 )
  {
    if ( *(_DWORD *)(v3 + 396) == 2 )
    {
      v6 = (struct CAppInfo *)a1[1];
      if ( v6 )
      {
        StringToGuid(a2, &v9);
        if ( *((_QWORD *)v6 + 3) == *(_QWORD *)&v9.Data1 && *((_QWORD *)v6 + 4) == *(_QWORD *)v9.Data4 )
          goto LABEL_8;
        v8 = v9;
        v6 = CAppList::Find((CAppList *)(v3 + 32), &v8);
        if ( v6 )
        {
          CAppInfo::SetRsopFailureStatus((CAppInfo *)a1[1], 31, a3);
LABEL_8:
          CAppInfo::SetRsopFailureStatus(v6, 31, a3);
        }
      }
    }
  }
  return 0;
}

```

## disassembly

```asm
0x180004d60  mov     [rsp+arg_10], rbx
0x180004d65  push    rbp
0x180004d66  push    rsi
0x180004d67  push    rdi
0x180004d68  sub     rsp, 50h
0x180004d6c  mov     rax, cs:__security_cookie
0x180004d73  xor     rax, rsp
0x180004d76  mov     [rsp+68h+var_28], rax
0x180004d7b  mov     rsi, [rcx]
0x180004d7e  xorps   xmm0, xmm0
0x180004d81  mov     ebp, r8d
0x180004d84  mov     rax, rdx
0x180004d87  mov     rdi, rcx
0x180004d8a  movups  xmmword ptr [rsp+68h+var_38.Data1], xmm0
0x180004d8f  test    rsi, rsi
0x180004d92  jz      short loc_180004E0B
0x180004d94  cmp     dword ptr [rsi+18Ch], 2
0x180004d9b  jnz     short loc_180004E0B
0x180004d9d  mov     rbx, [rcx+8]
0x180004da1  test    rbx, rbx
0x180004da4  jz      short loc_180004E0B
0x180004da6  lea     rdx, [rsp+68h+var_38]; struct _GUID *
0x180004dab  mov     rcx, rax; unsigned __int16 *
0x180004dae  call    ?StringToGuid@@YAXPEBGPEAU_GUID@@@Z; StringToGuid(ushort const *,_GUID *)
0x180004db3  mov     rax, [rbx+18h]
0x180004db7  cmp     rax, qword ptr [rsp+68h+var_38.Data1]
0x180004dbc  jnz     short loc_180004DC9
0x180004dbe  mov     rax, [rbx+20h]
0x180004dc2  cmp     rax, qword ptr [rsp+68h+var_38.Data4]
0x180004dc7  jz      short loc_180004DFB
0x180004dc9  movaps  xmm0, xmmword ptr [rsp+68h+var_38.Data1]
0x180004dce  lea     rcx, [rsi+20h]; this
0x180004dd2  lea     rdx, [rsp+68h+var_48]; struct _GUID
0x180004dd7  movdqa  xmmword ptr [rsp+68h+var_48.Data1], xmm0
0x180004ddd  call    ?Find@CAppList@@QEAAPEAVCAppInfo@@U_GUID@@@Z; CAppList::Find(_GUID)
0x180004de2  mov     rbx, rax
0x180004de5  test    rax, rax
0x180004de8  jz      short loc_180004E0B
0x180004dea  mov     rcx, [rdi+8]; this
0x180004dee  mov     r8d, ebp; unsigned int
0x180004df1  mov     edx, 1Fh; unsigned int
0x180004df6  call    ?SetRsopFailureStatus@CAppInfo@@QEAAXKK@Z; CAppInfo::SetRsopFailureStatus(ulong,ulong)
0x180004dfb  mov     r8d, ebp; unsigned int
0x180004dfe  mov     edx, 1Fh; unsigned int
0x180004e03  mov     rcx, rbx; this
0x180004e06  call    ?SetRsopFailureStatus@CAppInfo@@QEAAXKK@Z; CAppInfo::SetRsopFailureStatus(ulong,ulong)
0x180004e0b  xor     eax, eax
0x180004e0d  mov     rcx, [rsp+68h+var_28]
0x180004e12  xor     rcx, rsp; StackCookie
0x180004e15  call    __security_check_cookie
0x180004e1a  mov     rbx, [rsp+68h+arg_10]
0x180004e22  add     rsp, 50h
0x180004e26  pop     rdi
0x180004e27  pop     rsi
0x180004e28  pop     rbp
0x180004e29  retn
```
