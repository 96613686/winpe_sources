# wil::details_abi::ThreadLocalData::GetCaughtExceptionError(wil::FailureInfo &,uint,wil::DiagnosticsInfo const *,long,void *)

- ea: `0x18001fb88`
- end: `0x18001fcef`
- name: `?GetCaughtExceptionError@ThreadLocalData@details_abi@wil@@QEBA_NAEAUFailureInfo@3@IPEBUDiagnosticsInfo@3@JPEAX@Z`
- size: `359`
- prototype: `bool __fastcall(wil::details_abi::ThreadLocalData *__hidden this, struct wil::FailureInfo *, unsigned int, const struct DiagnosticsInfo *, int, void *)`
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x18001fb54`

## callees

- `0x180003560`
- `0x180003fd4`
- `0x18000fcdc`
- `0x18001fb88`
- `0x18001ffa0`
- `0x180021400`
- `0x18002e660`

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
0x18001fb88  mov     [rsp-8+arg_10], rbx
0x18001fb8d  push    rbp
0x18001fb8e  push    rsi
0x18001fb8f  push    rdi
0x18001fb90  push    r12
0x18001fb92  push    r13
0x18001fb94  push    r14
0x18001fb96  push    r15
0x18001fb98  lea     rbp, [rsp-1010h]
0x18001fba0  mov     eax, 1110h
0x18001fba5  call    _alloca_probe
0x18001fbaa  sub     rsp, rax
0x18001fbad  mov     rax, cs:__security_cookie
0x18001fbb4  xor     rax, rsp
0x18001fbb7  mov     [rbp+1040h+var_40], rax
0x18001fbbe  mov     r13, [rbp+1040h+arg_28]
0x18001fbc5  mov     r15d, r8d
0x18001fbc8  mov     rbx, rdx
0x18001fbcb  mov     r12, rcx
0x18001fbce  xor     edx, edx; Val
0x18001fbd0  lea     rcx, [rsp+1140h+var_10F0]; void *
0x18001fbd5  mov     r8d, 98h; Size
0x18001fbdb  mov     rdi, r9
0x18001fbde  call    memset_0
0x18001fbe3  xor     r9d, r9d; int
0x18001fbe6  lea     rdx, [rsp+1140h+var_10F0]; struct wil::FailureInfo *
0x18001fbeb  mov     r8d, r15d; unsigned int
0x18001fbee  mov     rcx, r12; this
0x18001fbf1  call    ?GetLastError@ThreadLocalData@details_abi@wil@@QEBA_NAEAUFailureInfo@3@IJ@Z; wil::details_abi::ThreadLocalData::GetLastError(wil::FailureInfo &,uint,long)
0x18001fbf6  test    al, al
0x18001fbf8  jz      short loc_18001FC61
0x18001fbfa  call    ?ResultFromCaughtException@wil@@YAJXZ; wil::ResultFromCaughtException(void)
0x18001fbff  cmp     dword ptr [rsp+1140h+var_10F0+8], eax
0x18001fc03  jnz     short loc_18001FC61
0x18001fc05  movaps  xmm0, [rsp+1140h+var_10F0]
0x18001fc0a  movaps  xmm1, [rsp+1140h+var_10E0]
0x18001fc0f  mov     rax, [rbp+1040h+var_1060]
0x18001fc13  movups  xmmword ptr [rbx], xmm0
0x18001fc16  movaps  xmm0, [rsp+1140h+var_10D0]
0x18001fc1b  movups  xmmword ptr [rbx+10h], xmm1
0x18001fc1f  movaps  xmm1, [rbp+1040h+var_10C0]
0x18001fc23  movups  xmmword ptr [rbx+20h], xmm0
0x18001fc27  movaps  xmm0, [rbp+1040h+var_10B0]
0x18001fc2b  movups  xmmword ptr [rbx+30h], xmm1
0x18001fc2f  movaps  xmm1, [rbp+1040h+var_10A0]
0x18001fc33  movups  xmmword ptr [rbx+40h], xmm0
0x18001fc37  movaps  xmm0, [rbp+1040h+var_1090]
0x18001fc3b  movups  xmmword ptr [rbx+50h], xmm1
0x18001fc3f  movaps  xmm1, [rbp+1040h+var_1080]
0x18001fc43  movups  xmmword ptr [rbx+60h], xmm0
0x18001fc47  movaps  xmm0, [rbp+1040h+var_1070]
0x18001fc4b  movups  xmmword ptr [rbx+70h], xmm1
0x18001fc4f  movups  xmmword ptr [rbx+80h], xmm0
0x18001fc56  mov     [rbx+90h], rax
0x18001fc5d  mov     al, 1
0x18001fc5f  jmp     short loc_18001FCC5
0x18001fc61  test    rdi, rdi
0x18001fc64  jz      short loc_18001FC73
0x18001fc66  mov     rsi, [rdi]
0x18001fc69  mov     r14, [rdi+8]
0x18001fc6d  movzx   edi, word ptr [rdi+18h]
0x18001fc71  jmp     short loc_18001FC7A
0x18001fc73  xor     esi, esi
0x18001fc75  xor     edi, edi
0x18001fc77  xor     r14d, r14d
0x18001fc7a  xor     edx, edx; Val
0x18001fc7c  lea     rcx, [rbp+1040h+var_1040]; void *
0x18001fc80  mov     r8d, 1000h; Size
0x18001fc86  call    memset_0
0x18001fc8b  lea     rax, [rbp+1040h+var_1040]
0x18001fc8f  mov     [rsp+1140h+var_10F8], 2
0x18001fc97  mov     [rsp+1140h+var_1108], rax
0x18001fc9c  lea     rcx, [rbp+1040h+var_1050]
0x18001fca0  movzx   r8d, di
0x18001fca4  mov     r9, r14
0x18001fca7  mov     rdx, rsi
0x18001fcaa  mov     [rsp+1140h+var_1110], r13
0x18001fcaf  call    ??$ReportFailure_CaughtExceptionCommon@$01@details@wil@@YA?AUResultStatus@01@PEAXIPEBD110PEA_W_KW4SupportedExceptions@1@@Z; wil::details::ReportFailure_CaughtExceptionCommon<2>(void *,uint,char const *,char const *,char const *,void *,wchar_t *,unsigned __int64,wil::SupportedExceptions)
0x18001fcb4  mov     r8d, r15d; unsigned int
0x18001fcb7  mov     rdx, rbx; struct wil::FailureInfo *
0x18001fcba  mov     rcx, r12; this
0x18001fcbd  mov     r9d, [rax]; int
0x18001fcc0  call    ?GetLastError@ThreadLocalData@details_abi@wil@@QEBA_NAEAUFailureInfo@3@IJ@Z; wil::details_abi::ThreadLocalData::GetLastError(wil::FailureInfo &,uint,long)
0x18001fcc5  mov     rcx, [rbp+1040h+var_40]
0x18001fccc  xor     rcx, rsp; StackCookie
0x18001fccf  call    __security_check_cookie
0x18001fcd4  mov     rbx, [rsp+1140h+arg_10]
0x18001fcdc  add     rsp, 1110h
0x18001fce3  pop     r15
0x18001fce5  pop     r14
0x18001fce7  pop     r13
0x18001fce9  pop     r12
0x18001fceb  pop     rdi
0x18001fcec  pop     rsi
0x18001fced  pop     rbp
0x18001fcee  retn
```
