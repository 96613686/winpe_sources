# wil::details_abi::ThreadLocalData::GetCaughtExceptionError(wil::FailureInfo &,uint,wil::DiagnosticsInfo const *,long,void *)

- ea: `0x180014c5c`
- end: `0x180014dc3`
- name: `?GetCaughtExceptionError@ThreadLocalData@details_abi@wil@@QEBA_NAEAUFailureInfo@3@IPEBUDiagnosticsInfo@3@JPEAX@Z`
- size: `359`
- prototype: `bool __fastcall(wil::details_abi::ThreadLocalData *__hidden this, struct wil::FailureInfo *, unsigned int, const struct DiagnosticsInfo *, int, void *)`
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x180014c28`

## callees

- `0x180002380`
- `0x1800032dc`
- `0x18000ae08`
- `0x180014c5c`
- `0x180015550`
- `0x180018aa0`
- `0x1800227b0`

## pseudocode

```c
bool __fastcall wil::details_abi::ThreadLocalData::GetCaughtExceptionError(
        wil::details_abi::ThreadLocalData *this,
        struct wil::FailureInfo *a2,
        unsigned int a3,
        const struct DiagnosticsInfo *a4,
        int a5,
        void *a6)
{
  wil *v10; // rcx
  int v11; // eax
  __int128 v12; // xmm1
  __int64 v13; // rax
  __int128 v14; // xmm0
  __int128 v15; // xmm1
  __int128 v16; // xmm0
  __int128 v17; // xmm1
  __int128 v18; // xmm0
  __int128 v19; // xmm1
  __int128 v20; // xmm0
  __int64 v22; // rsi
  struct DiagnosticsInfo v23; // r14
  unsigned __int16 cost; // di
  int *v25; // rax
  int v26; // [rsp+20h] [rbp-E0h]
  int v27; // [rsp+28h] [rbp-D8h]
  int v28; // [rsp+40h] [rbp-C0h]
  _OWORD v29[9]; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v30; // [rsp+E0h] [rbp-20h]
  _BYTE v31[16]; // [rsp+F0h] [rbp-10h] BYREF
  _BYTE v32[4096]; // [rsp+100h] [rbp+0h] BYREF

  memset_0(v29, 0, 0x98u);
  if ( wil::details_abi::ThreadLocalData::GetLastError(this, (struct wil::FailureInfo *)v29, a3, 0)
    && (v11 = wil::ResultFromCaughtException(v10), DWORD2(v29[0]) == v11) )
  {
    v12 = v29[1];
    v13 = v30;
    *(_OWORD *)a2 = v29[0];
    v14 = v29[2];
    *((_OWORD *)a2 + 1) = v12;
    v15 = v29[3];
    *((_OWORD *)a2 + 2) = v14;
    v16 = v29[4];
    *((_OWORD *)a2 + 3) = v15;
    v17 = v29[5];
    *((_OWORD *)a2 + 4) = v16;
    v18 = v29[6];
    *((_OWORD *)a2 + 5) = v17;
    v19 = v29[7];
    *((_OWORD *)a2 + 6) = v18;
    v20 = v29[8];
    *((_OWORD *)a2 + 7) = v19;
    *((_OWORD *)a2 + 8) = v20;
    *((_QWORD *)a2 + 18) = v13;
    return 1;
  }
  else
  {
    if ( a4 )
    {
      v22 = (__int64)*a4;
      v23 = a4[1];
      cost = a4[3].cost;
    }
    else
    {
      LODWORD(v22) = 0;
      cost = 0;
      v23.cost = 0;
    }
    memset_0(v32, 0, sizeof(v32));
    v25 = (int *)wil::details::ReportFailure_CaughtExceptionCommon<2>(
                   (__int64)v31,
                   v22,
                   cost,
                   v23.cost,
                   v26,
                   v27,
                   (__int64)a6,
                   (__int64)v32,
                   v28,
                   2);
    return wil::details_abi::ThreadLocalData::GetLastError(this, a2, a3, *v25);
  }
}

```

## disassembly

```asm
0x180014c5c  mov     [rsp-8+arg_10], rbx
0x180014c61  push    rbp
0x180014c62  push    rsi
0x180014c63  push    rdi
0x180014c64  push    r12
0x180014c66  push    r13
0x180014c68  push    r14
0x180014c6a  push    r15
0x180014c6c  lea     rbp, [rsp-1010h]
0x180014c74  mov     eax, 1110h
0x180014c79  call    _alloca_probe
0x180014c7e  sub     rsp, rax
0x180014c81  mov     rax, cs:__security_cookie
0x180014c88  xor     rax, rsp
0x180014c8b  mov     [rbp+1040h+var_40], rax
0x180014c92  mov     r13, [rbp+1040h+arg_28]
0x180014c99  mov     r15d, r8d
0x180014c9c  mov     rbx, rdx
0x180014c9f  mov     r12, rcx
0x180014ca2  xor     edx, edx; Val
0x180014ca4  lea     rcx, [rsp+1140h+var_10F0]; void *
0x180014ca9  mov     r8d, 98h; Size
0x180014caf  mov     rdi, r9
0x180014cb2  call    memset_0
0x180014cb7  xor     r9d, r9d; int
0x180014cba  lea     rdx, [rsp+1140h+var_10F0]; struct wil::FailureInfo *
0x180014cbf  mov     r8d, r15d; unsigned int
0x180014cc2  mov     rcx, r12; this
0x180014cc5  call    ?GetLastError@ThreadLocalData@details_abi@wil@@QEBA_NAEAUFailureInfo@3@IJ@Z; wil::details_abi::ThreadLocalData::GetLastError(wil::FailureInfo &,uint,long)
0x180014cca  test    al, al
0x180014ccc  jz      short loc_180014D35
0x180014cce  call    ?ResultFromCaughtException@wil@@YAJXZ; wil::ResultFromCaughtException(void)
0x180014cd3  cmp     dword ptr [rsp+1140h+var_10F0+8], eax
0x180014cd7  jnz     short loc_180014D35
0x180014cd9  movaps  xmm0, [rsp+1140h+var_10F0]
0x180014cde  movaps  xmm1, [rsp+1140h+var_10E0]
0x180014ce3  mov     rax, [rbp+1040h+var_1060]
0x180014ce7  movups  xmmword ptr [rbx], xmm0
0x180014cea  movaps  xmm0, [rsp+1140h+var_10D0]
0x180014cef  movups  xmmword ptr [rbx+10h], xmm1
0x180014cf3  movaps  xmm1, [rbp+1040h+var_10C0]
0x180014cf7  movups  xmmword ptr [rbx+20h], xmm0
0x180014cfb  movaps  xmm0, [rbp+1040h+var_10B0]
0x180014cff  movups  xmmword ptr [rbx+30h], xmm1
0x180014d03  movaps  xmm1, [rbp+1040h+var_10A0]
0x180014d07  movups  xmmword ptr [rbx+40h], xmm0
0x180014d0b  movaps  xmm0, [rbp+1040h+var_1090]
0x180014d0f  movups  xmmword ptr [rbx+50h], xmm1
0x180014d13  movaps  xmm1, [rbp+1040h+var_1080]
0x180014d17  movups  xmmword ptr [rbx+60h], xmm0
0x180014d1b  movaps  xmm0, [rbp+1040h+var_1070]
0x180014d1f  movups  xmmword ptr [rbx+70h], xmm1
0x180014d23  movups  xmmword ptr [rbx+80h], xmm0
0x180014d2a  mov     [rbx+90h], rax
0x180014d31  mov     al, 1
0x180014d33  jmp     short loc_180014D99
0x180014d35  test    rdi, rdi
0x180014d38  jz      short loc_180014D47
0x180014d3a  mov     rsi, [rdi]
0x180014d3d  mov     r14, [rdi+8]
0x180014d41  movzx   edi, word ptr [rdi+18h]
0x180014d45  jmp     short loc_180014D4E
0x180014d47  xor     esi, esi
0x180014d49  xor     edi, edi
0x180014d4b  xor     r14d, r14d
0x180014d4e  xor     edx, edx; Val
0x180014d50  lea     rcx, [rbp+1040h+var_1040]; void *
0x180014d54  mov     r8d, 1000h; Size
0x180014d5a  call    memset_0
0x180014d5f  lea     rax, [rbp+1040h+var_1040]
0x180014d63  mov     [rsp+1140h+var_10F8], 2
0x180014d6b  mov     [rsp+1140h+var_1108], rax
0x180014d70  lea     rcx, [rbp+1040h+var_1050]
0x180014d74  movzx   r8d, di
0x180014d78  mov     r9, r14
0x180014d7b  mov     rdx, rsi
0x180014d7e  mov     [rsp+1140h+var_1110], r13
0x180014d83  call    ??$ReportFailure_CaughtExceptionCommon@$01@details@wil@@YA?AUResultStatus@01@PEAXIPEBD110PEAG_KW4SupportedExceptions@1@@Z; wil::details::ReportFailure_CaughtExceptionCommon<2>(void *,uint,char const *,char const *,char const *,void *,ushort *,unsigned __int64,wil::SupportedExceptions)
0x180014d88  mov     r8d, r15d; unsigned int
0x180014d8b  mov     rdx, rbx; struct wil::FailureInfo *
0x180014d8e  mov     rcx, r12; this
0x180014d91  mov     r9d, [rax]; int
0x180014d94  call    ?GetLastError@ThreadLocalData@details_abi@wil@@QEBA_NAEAUFailureInfo@3@IJ@Z; wil::details_abi::ThreadLocalData::GetLastError(wil::FailureInfo &,uint,long)
0x180014d99  mov     rcx, [rbp+1040h+var_40]
0x180014da0  xor     rcx, rsp; StackCookie
0x180014da3  call    __security_check_cookie
0x180014da8  mov     rbx, [rsp+1140h+arg_10]
0x180014db0  add     rsp, 1110h
0x180014db7  pop     r15
0x180014db9  pop     r14
0x180014dbb  pop     r13
0x180014dbd  pop     r12
0x180014dbf  pop     rdi
0x180014dc0  pop     rsi
0x180014dc1  pop     rbp
0x180014dc2  retn
```
