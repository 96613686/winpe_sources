# CRemoteTextConnection::ReportPredictedKeyEvent(ushort,Windows::System::RemoteDesktop::Input::RemoteKeyEventAttributes)

- ea: `0x180036960`
- end: `0x180036a78`
- name: `?ReportPredictedKeyEvent@CRemoteTextConnection@@UEAAJGW4RemoteKeyEventAttributes@Input@RemoteDesktop@System@Windows@@@Z`
- size: `280`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x180012030`
- `0x180036960`
- `0x180058010`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1800369f3`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1800369f3`
- `CoreMessaging!MsgBlobCreateShared` at `0x1800369d7`
- `CoreMessaging!MsgBlobCreateShared` at `0x1800369d7`
- `CoreMessaging!MsgRelease` at `0x180036a46`
- `CoreMessaging!MsgRelease` at `0x180036a46`

## pseudocode

```c
__int64 __fastcall CRemoteTextConnection::ReportPredictedKeyEvent(__int64 a1, unsigned __int16 a2, char a3)
{
  __int64 v5; // rax
  char v6; // al
  int v7; // r14d
  char v8; // cl
  char v9; // al
  __int64 v10; // rsi
  __int64 (__fastcall *v11)(_QWORD, _QWORD, _QWORD, _QWORD); // rdi
  int v12; // eax
  __int64 v13; // rdx
  __int64 v14; // r8
  __int64 v15; // r9
  int v17; // [rsp+20h] [rbp-68h]
  _OWORD v18[4]; // [rsp+40h] [rbp-48h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+0h]
  __int64 v20; // [rsp+90h] [rbp+8h] BYREF

  if ( *(_QWORD *)(a1 + 96) )
  {
    v5 = *(_QWORD *)(a1 + 72);
    if ( *(_DWORD *)(v5 + 32) > 1u || (*(_BYTE *)(v5 + 36) & 8) != 0 )
    {
      v6 = *(_BYTE *)(a2 + a1 + 104);
      v7 = a3 & 1;
      v8 = v6 | 0x80;
      v9 = v6 & 0x7F;
      if ( (a3 & 1) != 0 )
        v8 = v9;
      *(_BYTE *)(a2 + a1 + 104) = v8;
      v20 = 0;
      MsgBlobCreateShared(a1 + 104, 256, &v20);
      v10 = *(_QWORD *)(a1 + 96);
      v11 = *(__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD, _QWORD))(*(_QWORD *)v10 + 224LL);
      GetTickCount();
      v18[0] = *(_OWORD *)(a1 + 360);
      v12 = v11(v10, v18, a2, 0);
      if ( v12 < 0 )
      {
        LOWORD(v17) = v7 != 0 ? 2052 : 2049;
        wil::details::in1diag3::_FailFast_Hr(
          retaddr,
          (void *)0xA6,
          (unsigned int)"mincore\\textinput\\dev\\virtualization\\remotetextconnection\\remotetextconnection.cpp",
          (const char *)(unsigned int)v12,
          v17);
      }
      MsgRelease(v20, v13, v14, v15);
    }
  }
  return 0;
}

```

## disassembly

```asm
0x180036960  push    rbx
0x180036962  push    rbp
0x180036963  push    rsi
0x180036964  push    rdi
0x180036965  push    r14
0x180036967  push    r15
0x180036969  sub     rsp, 58h
0x18003696d  cmp     qword ptr [rcx+60h], 0
0x180036972  mov     r14d, r8d
0x180036975  movzx   r15d, dx
0x180036979  mov     rbp, rcx
0x18003697c  jz      loc_180036A4C
0x180036982  mov     rax, [rcx+48h]
0x180036986  cmp     dword ptr [rax+20h], 1
0x18003698a  ja      short loc_180036996
0x18003698c  test    byte ptr [rax+24h], 8
0x180036990  jz      loc_180036A4C
0x180036996  mov     cl, [r15+rcx+68h]
0x18003699b  lea     r8, [rsp+88h+arg_0]
0x1800369a3  mov     al, cl
0x1800369a5  and     r14d, 1
0x1800369a9  or      cl, 80h
0x1800369ac  and     al, 7Fh
0x1800369ae  mov     dl, r14b
0x1800369b1  movzx   ecx, cl
0x1800369b4  xor     dl, 1
0x1800369b7  movzx   eax, al
0x1800369ba  mov     edx, 100h
0x1800369bf  cmovz   ecx, eax
0x1800369c2  mov     [r15+rbp+68h], cl
0x1800369c7  lea     rcx, [rbp+68h]
0x1800369cb  mov     [rsp+88h+arg_0], 0
0x1800369d7  call    cs:__imp_MsgBlobCreateShared
0x1800369dd  mov     rsi, [rbp+60h]
0x1800369e1  mov     rbx, [rsp+88h+arg_0]
0x1800369e9  mov     rax, [rsi]
0x1800369ec  mov     rdi, [rax+0E0h]
0x1800369f3  call    cs:__imp_GetTickCount
0x1800369f9  movups  xmm0, xmmword ptr [rbp+168h]
0x180036a00  mov     [rsp+88h+var_58], rbx
0x180036a05  neg     r14d
0x180036a08  mov     [rsp+88h+var_60], eax
0x180036a0c  movzx   r8d, r15w
0x180036a10  sbb     dx, dx
0x180036a13  mov     rcx, rsi
0x180036a16  and     dx, 3
0x180036a1a  xor     r9d, r9d
0x180036a1d  add     dx, 801h
0x180036a22  mov     rax, rdi
0x180036a25  mov     word ptr [rsp+88h+var_68], dx; int
0x180036a2a  lea     rdx, [rsp+88h+var_48]
0x180036a2f  movdqu  [rsp+88h+var_48], xmm0
0x180036a35  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180036a3a  test    eax, eax
0x180036a3c  js      short loc_180036A5B
0x180036a3e  mov     rcx, [rsp+88h+arg_0]
0x180036a46  call    cs:__imp_MsgRelease
0x180036a4c  xor     eax, eax
0x180036a4e  add     rsp, 58h
0x180036a52  pop     r15
0x180036a54  pop     r14
0x180036a56  pop     rdi
0x180036a57  pop     rsi
0x180036a58  pop     rbp
0x180036a59  pop     rbx
0x180036a5a  retn
0x180036a5b  mov     rcx, [rsp+88h]; this
0x180036a63  lea     r8, aMincoreTextinp_1; "mincore\\textinput\\dev\\virtualization"...
0x180036a6a  mov     r9d, eax; char *
0x180036a6d  mov     edx, 0A6h; void *
0x180036a72  call    ?_FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_FailFast_Hr(void *,uint,char const *,long)
```
