# CanMakePaymentRequest::CanMakePaymentRequest(_PaymentServiceRequest const *,void *,ushort const *)

- ea: `0x180085a1c`
- end: `0x180085be5`
- name: `??0CanMakePaymentRequest@@QEAA@PEBU_PaymentServiceRequest@@PEAXPEBG@Z`
- size: `457`
- prototype: `CanMakePaymentRequest *__fastcall(CanMakePaymentRequest *__hidden this, const struct _PaymentServiceRequest *, void *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `6`
- tags: `service_task`

## callers

- `0x180084ca4`

## callees

- `0x180004ec0`
- `0x18000e4c8`
- `0x180085a1c`
- `0x180085d38`
- `0x1800868b0`
- `0x1800889c4`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x180085b5b`
- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x180085b5b`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionEx` at `0x180085af5`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionEx` at `0x180085af5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180085b69`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180085b78`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180085b69`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180085b78`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180085b97`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180085b97`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180085b83`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180085b83`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
CanMakePaymentRequest *__fastcall CanMakePaymentRequest::CanMakePaymentRequest(
        CanMakePaymentRequest *this,
        const struct _PaymentServiceRequest *a2,
        void *a3,
        const unsigned __int16 *a4)
{
  __int64 v7; // rax
  __int128 v8; // xmm1
  __int128 v9; // xmm2
  __int128 v10; // xmm3
  __int128 v11; // xmm4
  __int128 v12; // xmm5
  __int128 v13; // xmm6
  __int128 v14; // xmm7
  __int128 v15; // xmm8
  __int128 v16; // xmm9
  __int64 v17; // rcx
  void *v18; // rdx
  HANDLE Event; // rsi
  unsigned int v20; // r8d
  const char *v21; // r9
  void *v22; // rbx
  DWORD LastError; // edi
  unsigned int v24; // r8d
  const char *v25; // r9
  _DWORD *v27; // [rsp+20h] [rbp-128h]
  _BYTE v28[240]; // [rsp+28h] [rbp-120h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+148h] [rbp+0h]

  *(_DWORD *)this = 0;
  *((_BYTE *)this + 4) = 0;
  *((_QWORD *)this + 1) = 0;
  *((_QWORD *)this + 2) = 0;
  v7 = CopyPaymentServiceRequest((__int64)v28, (__int64)a2);
  v8 = *(_OWORD *)(v7 + 16);
  v9 = *(_OWORD *)(v7 + 32);
  v10 = *(_OWORD *)(v7 + 48);
  v11 = *(_OWORD *)(v7 + 64);
  v12 = *(_OWORD *)(v7 + 80);
  v13 = *(_OWORD *)(v7 + 96);
  v14 = *(_OWORD *)(v7 + 112);
  v15 = *(_OWORD *)(v7 + 128);
  v16 = *(_OWORD *)(v7 + 144);
  v17 = *(_QWORD *)(v7 + 160);
  *(_OWORD *)((char *)this + 24) = *(_OWORD *)v7;
  *(_OWORD *)((char *)this + 40) = v8;
  *(_OWORD *)((char *)this + 56) = v9;
  *(_OWORD *)((char *)this + 72) = v10;
  *(_OWORD *)((char *)this + 88) = v11;
  *(_OWORD *)((char *)this + 104) = v12;
  *(_OWORD *)((char *)this + 120) = v13;
  *(_OWORD *)((char *)this + 136) = v14;
  *(_OWORD *)((char *)this + 152) = v15;
  *(_OWORD *)((char *)this + 168) = v16;
  *((_QWORD *)this + 23) = v17;
  InitializeCriticalSectionEx((LPCRITICAL_SECTION)((char *)this + 192), 0, 0);
  v27 = operator new(0x48u);
  *(_OWORD *)v27 = 0;
  v27[2] = 1;
  v27[3] = 1;
  *(_QWORD *)v27 = &std::_Ref_count_obj2<CanMakePaymentRequestSource>::`vftable';
  CanMakePaymentRequestSource::CanMakePaymentRequestSource((CanMakePaymentRequestSource *)(v27 + 4), a3, a4);
  *((_QWORD *)this + 29) = v27 + 4;
  *((_QWORD *)this + 30) = v27;
  Event = CreateEventExW(0, 0, 1u, 0x1F0003u);
  if ( !Event )
    wil::details::in1diag3::Throw_GetLastError(retaddr, v18, v20, v21);
  GetLastError();
  v22 = (void *)*((_QWORD *)this + 1);
  if ( v22 )
  {
    LastError = GetLastError();
    if ( !CloseHandle(v22) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v24, v25);
    SetLastError(LastError);
  }
  *((_QWORD *)this + 1) = Event;
  return this;
}

```

## disassembly

```asm
0x180085a1c  mov     rax, rsp
0x180085a1f  mov     [rax+8], rcx
0x180085a23  push    rbx
0x180085a24  push    rbp
0x180085a25  push    rsi
0x180085a26  push    rdi
0x180085a27  push    r14
0x180085a29  push    r15
0x180085a2b  sub     rsp, 118h
0x180085a32  movaps  xmmword ptr [rax-48h], xmm6
0x180085a36  movaps  xmmword ptr [rax-58h], xmm7
0x180085a3a  movaps  xmmword ptr [rax-68h], xmm8
0x180085a3f  movaps  xmmword ptr [rax-78h], xmm9
0x180085a44  mov     rbp, r9
0x180085a47  mov     r14, r8
0x180085a4a  mov     r15, rcx
0x180085a4d  mov     dword ptr [rcx], 0
0x180085a53  mov     byte ptr [rcx+4], 0
0x180085a57  mov     qword ptr [rcx+8], 0
0x180085a5f  mov     qword ptr [rcx+10h], 0
0x180085a67  lea     rcx, [rsp+148h+var_120]
0x180085a6c  call    ?CopyPaymentServiceRequest@@YA?AU_PaymentServiceRequest@@AEBU1@@Z; CopyPaymentServiceRequest(_PaymentServiceRequest const &)
0x180085a71  movups  xmm0, xmmword ptr [rax]
0x180085a74  movups  xmm1, xmmword ptr [rax+10h]
0x180085a78  movups  xmm2, xmmword ptr [rax+20h]
0x180085a7c  movups  xmm3, xmmword ptr [rax+30h]
0x180085a80  movups  xmm4, xmmword ptr [rax+40h]
0x180085a84  movups  xmm5, xmmword ptr [rax+50h]
0x180085a88  movups  xmm6, xmmword ptr [rax+60h]
0x180085a8c  movups  xmm7, xmmword ptr [rax+70h]
0x180085a90  movups  xmm8, xmmword ptr [rax+80h]
0x180085a98  movups  xmm9, xmmword ptr [rax+90h]
0x180085aa0  mov     rcx, [rax+0A0h]
0x180085aa7  movups  xmmword ptr [r15+18h], xmm0
0x180085aac  movups  xmmword ptr [r15+28h], xmm1
0x180085ab1  movups  xmmword ptr [r15+38h], xmm2
0x180085ab6  movups  xmmword ptr [r15+48h], xmm3
0x180085abb  movups  xmmword ptr [r15+58h], xmm4
0x180085ac0  movups  xmmword ptr [r15+68h], xmm5
0x180085ac5  movups  xmmword ptr [r15+78h], xmm6
0x180085aca  movups  xmmword ptr [r15+88h], xmm7
0x180085ad2  movups  xmmword ptr [r15+98h], xmm8
0x180085ada  movups  xmmword ptr [r15+0A8h], xmm9
0x180085ae2  mov     [r15+0B8h], rcx
0x180085ae9  lea     rcx, [r15+0C0h]; lpCriticalSection
0x180085af0  xor     r8d, r8d; Flags
0x180085af3  xor     edx, edx; dwSpinCount
0x180085af5  call    cs:__imp_InitializeCriticalSectionEx
0x180085afb  nop
0x180085afc  lea     rsi, [r15+0E8h]
0x180085b03  mov     ecx, 48h ; 'H'; Size
0x180085b08  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180085b0d  mov     rdi, rax
0x180085b10  mov     [rsp+148h+var_128], rax
0x180085b15  xorps   xmm0, xmm0
0x180085b18  movups  xmmword ptr [rax], xmm0
0x180085b1b  mov     dword ptr [rax+8], 1
0x180085b22  mov     dword ptr [rax+0Ch], 1
0x180085b29  lea     rax, ??_7?$_Ref_count_obj2@VCanMakePaymentRequestSource@@@std@@6B@; const std::_Ref_count_obj2<CanMakePaymentRequestSource>::`vftable'
0x180085b30  mov     [rdi], rax
0x180085b33  lea     rbx, [rdi+10h]
0x180085b37  mov     r8, rbp; unsigned __int16 *
0x180085b3a  mov     rdx, r14; void *
0x180085b3d  mov     rcx, rbx; this
0x180085b40  call    ??0CanMakePaymentRequestSource@@QEAA@PEAXPEBG@Z; CanMakePaymentRequestSource::CanMakePaymentRequestSource(void *,ushort const *)
0x180085b45  nop
0x180085b46  mov     [rsi], rbx
0x180085b49  mov     [rsi+8], rdi
0x180085b4d  xor     edx, edx; lpName
0x180085b4f  xor     ecx, ecx; lpEventAttributes
0x180085b51  mov     r9d, 1F0003h; dwDesiredAccess
0x180085b57  lea     r8d, [rdx+1]; dwFlags
0x180085b5b  call    cs:__imp_CreateEventExW
0x180085b61  mov     rsi, rax
0x180085b64  test    rax, rax
0x180085b67  jz      short loc_180085BD7
0x180085b69  call    cs:__imp_GetLastError
0x180085b6f  mov     rbx, [r15+8]
0x180085b73  test    rbx, rbx
0x180085b76  jz      short loc_180085B9D
0x180085b78  call    cs:__imp_GetLastError
0x180085b7e  mov     edi, eax
0x180085b80  mov     rcx, rbx; hObject
0x180085b83  call    cs:__imp_CloseHandle
0x180085b89  mov     rcx, [rsp+148h]; this
0x180085b91  test    eax, eax
0x180085b93  jz      short loc_180085BCC
0x180085b95  mov     ecx, edi; dwErrCode
0x180085b97  call    cs:__imp_SetLastError
0x180085b9d  mov     [r15+8], rsi
0x180085ba1  mov     rax, r15
0x180085ba4  lea     r11, [rsp+148h+var_30]
0x180085bac  movaps  xmm6, xmmword ptr [r11-18h]
0x180085bb1  movaps  xmm7, xmmword ptr [r11-28h]
0x180085bb6  movaps  xmm8, xmmword ptr [r11-38h]
0x180085bbb  movaps  xmm9, xmmword ptr [r11-48h]
0x180085bc0  mov     rsp, r11
0x180085bc3  pop     r15
0x180085bc5  pop     r14
0x180085bc7  pop     rdi
0x180085bc8  pop     rsi
0x180085bc9  pop     rbp
0x180085bca  pop     rbx
0x180085bcb  retn
0x180085bcc  mov     edx, 0A0Bh; void *
0x180085bd1  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180085bd7  mov     rcx, [rsp+148h]; this
0x180085bdf  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
```
