# wil::details_abi::ThreadLocalData::GetCaughtExceptionError(wil::FailureInfo &,uint,wil::DiagnosticsInfo const *,long,void *)

- ea: `0x180030a18`
- end: `0x180030b7f`
- name: `?GetCaughtExceptionError@ThreadLocalData@details_abi@wil@@QEBA_NAEAUFailureInfo@3@IPEBUDiagnosticsInfo@3@JPEAX@Z`
- size: `359`
- prototype: `bool __fastcall(wil::details_abi::ThreadLocalData *__hidden this, struct wil::FailureInfo *, unsigned int, const struct DiagnosticsInfo *, int, void *)`
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x1800309e4`

## callees

- `0x18001d488`
- `0x18002a030`
- `0x18002aad0`
- `0x180030a18`
- `0x180030ce0`
- `0x1800315e0`
- `0x18003d850`

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
0x180030a18  mov     [rsp-8+arg_10], rbx
0x180030a1d  push    rbp
0x180030a1e  push    rsi
0x180030a1f  push    rdi
0x180030a20  push    r12
0x180030a22  push    r13
0x180030a24  push    r14
0x180030a26  push    r15
0x180030a28  lea     rbp, [rsp-1010h]
0x180030a30  mov     eax, 1110h
0x180030a35  call    _alloca_probe
0x180030a3a  sub     rsp, rax
0x180030a3d  mov     rax, cs:__security_cookie
0x180030a44  xor     rax, rsp
0x180030a47  mov     [rbp+1040h+var_40], rax
0x180030a4e  mov     r13, [rbp+1040h+arg_28]
0x180030a55  mov     r15d, r8d
0x180030a58  mov     rbx, rdx
0x180030a5b  mov     r12, rcx
0x180030a5e  xor     edx, edx; Val
0x180030a60  lea     rcx, [rsp+1140h+var_10F0]; void *
0x180030a65  mov     r8d, 98h; Size
0x180030a6b  mov     rdi, r9
0x180030a6e  call    memset_0
0x180030a73  xor     r9d, r9d; int
0x180030a76  lea     rdx, [rsp+1140h+var_10F0]; struct wil::FailureInfo *
0x180030a7b  mov     r8d, r15d; unsigned int
0x180030a7e  mov     rcx, r12; this
0x180030a81  call    ?GetLastError@ThreadLocalData@details_abi@wil@@QEBA_NAEAUFailureInfo@3@IJ@Z; wil::details_abi::ThreadLocalData::GetLastError(wil::FailureInfo &,uint,long)
0x180030a86  test    al, al
0x180030a88  jz      short loc_180030AF1
0x180030a8a  call    ?ResultFromCaughtException@wil@@YAJXZ; wil::ResultFromCaughtException(void)
0x180030a8f  cmp     dword ptr [rsp+1140h+var_10F0+8], eax
0x180030a93  jnz     short loc_180030AF1
0x180030a95  movaps  xmm0, [rsp+1140h+var_10F0]
0x180030a9a  movaps  xmm1, [rsp+1140h+var_10E0]
0x180030a9f  mov     rax, [rbp+1040h+var_1060]
0x180030aa3  movups  xmmword ptr [rbx], xmm0
0x180030aa6  movaps  xmm0, [rsp+1140h+var_10D0]
0x180030aab  movups  xmmword ptr [rbx+10h], xmm1
0x180030aaf  movaps  xmm1, [rbp+1040h+var_10C0]
0x180030ab3  movups  xmmword ptr [rbx+20h], xmm0
0x180030ab7  movaps  xmm0, [rbp+1040h+var_10B0]
0x180030abb  movups  xmmword ptr [rbx+30h], xmm1
0x180030abf  movaps  xmm1, [rbp+1040h+var_10A0]
0x180030ac3  movups  xmmword ptr [rbx+40h], xmm0
0x180030ac7  movaps  xmm0, [rbp+1040h+var_1090]
0x180030acb  movups  xmmword ptr [rbx+50h], xmm1
0x180030acf  movaps  xmm1, [rbp+1040h+var_1080]
0x180030ad3  movups  xmmword ptr [rbx+60h], xmm0
0x180030ad7  movaps  xmm0, [rbp+1040h+var_1070]
0x180030adb  movups  xmmword ptr [rbx+70h], xmm1
0x180030adf  movups  xmmword ptr [rbx+80h], xmm0
0x180030ae6  mov     [rbx+90h], rax
0x180030aed  mov     al, 1
0x180030aef  jmp     short loc_180030B55
0x180030af1  test    rdi, rdi
0x180030af4  jz      short loc_180030B03
0x180030af6  mov     rsi, [rdi]
0x180030af9  mov     r14, [rdi+8]
0x180030afd  movzx   edi, word ptr [rdi+18h]
0x180030b01  jmp     short loc_180030B0A
0x180030b03  xor     esi, esi
0x180030b05  xor     edi, edi
0x180030b07  xor     r14d, r14d
0x180030b0a  xor     edx, edx; Val
0x180030b0c  lea     rcx, [rbp+1040h+var_1040]; void *
0x180030b10  mov     r8d, 1000h; Size
0x180030b16  call    memset_0
0x180030b1b  lea     rax, [rbp+1040h+var_1040]
0x180030b1f  mov     [rsp+1140h+var_10F8], 2
0x180030b27  mov     [rsp+1140h+var_1108], rax
0x180030b2c  lea     rcx, [rbp+1040h+var_1050]
0x180030b30  movzx   r8d, di
0x180030b34  mov     r9, r14
0x180030b37  mov     rdx, rsi
0x180030b3a  mov     [rsp+1140h+var_1110], r13
0x180030b3f  call    ??$ReportFailure_CaughtExceptionCommon@$01@details@wil@@YA?AUResultStatus@01@PEAXIPEBD110PEAG_KW4SupportedExceptions@1@@Z; wil::details::ReportFailure_CaughtExceptionCommon<2>(void *,uint,char const *,char const *,char const *,void *,ushort *,unsigned __int64,wil::SupportedExceptions)
0x180030b44  mov     r8d, r15d; unsigned int
0x180030b47  mov     rdx, rbx; struct wil::FailureInfo *
0x180030b4a  mov     rcx, r12; this
0x180030b4d  mov     r9d, [rax]; int
0x180030b50  call    ?GetLastError@ThreadLocalData@details_abi@wil@@QEBA_NAEAUFailureInfo@3@IJ@Z; wil::details_abi::ThreadLocalData::GetLastError(wil::FailureInfo &,uint,long)
0x180030b55  mov     rcx, [rbp+1040h+var_40]
0x180030b5c  xor     rcx, rsp; StackCookie
0x180030b5f  call    __security_check_cookie
0x180030b64  mov     rbx, [rsp+1140h+arg_10]
0x180030b6c  add     rsp, 1110h
0x180030b73  pop     r15
0x180030b75  pop     r14
0x180030b77  pop     r13
0x180030b79  pop     r12
0x180030b7b  pop     rdi
0x180030b7c  pop     rsi
0x180030b7d  pop     rbp
0x180030b7e  retn
```
