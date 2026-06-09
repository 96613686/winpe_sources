# CServiceModule::OnCtfmonRequest(CPenSession *)

- ea: `0x18000f260`
- end: `0x18000f420`
- name: `?OnCtfmonRequest@CServiceModule@@QEAAXPEAVCPenSession@@@Z`
- size: `448`
- prototype: `void __fastcall(CServiceModule *__hidden this, struct CPenSession *)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, service_task`

## callers

- `0x18000ed70`

## callees

- `0x18000f260`
- `0x180014a80`
- `0x18001bbe0`
- `0x18002b3a8`
- `0x18002b404`

## import_xrefs

- `ntdll!EtwEventWriteTransfer` at `0x18000f38c`
- `ntdll!EtwEventWriteTransfer` at `0x18000f38c`

## string_xrefs

- `0x18000f2a3`: `PENSERVICE_CServiceModule::OnCtfmonRequest`
- `0x18000f3e5`: `PENSERVICE_CServiceModule::OnCtfmonRequest`

## pseudocode

```c
void __fastcall CServiceModule::OnCtfmonRequest(CServiceModule *this, struct CPenSession *a2)
{
  const struct CPenProcessInfo *v4; // rdx
  bool v5; // zf
  int v6; // eax
  _DWORD v7[2]; // [rsp+38h] [rbp-70h] BYREF
  __int64 v8; // [rsp+40h] [rbp-68h]
  __int128 v9; // [rsp+48h] [rbp-60h] BYREF
  __int64 v10; // [rsp+58h] [rbp-50h]
  __int16 *v11; // [rsp+60h] [rbp-48h] BYREF
  int v12; // [rsp+68h] [rbp-40h]
  int v13; // [rsp+6Ch] [rbp-3Ch]
  char *v14; // [rsp+70h] [rbp-38h]
  int v15; // [rsp+78h] [rbp-30h]
  int v16; // [rsp+7Ch] [rbp-2Ch]

  if ( WPP_GLOBAL_Control != (struct _GUID *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[1].Data4[4] & 0x10) != 0 )
    WPP_SF_sd(
      *(_QWORD *)&WPP_GLOBAL_Control[1].Data1,
      121,
      (unsigned int)WPP_689c0dbffb35351eabe1c9663a4c4c53_Traceguids,
      (unsigned int)"PENSERVICE_CServiceModule::OnCtfmonRequest",
      *((_DWORD *)a2 + 1));
  if ( (unsigned int)dword_1800411A8 > 5
    && (qword_1800411B8 & 0x4000000) != 0
    && (qword_1800411C0 & 0x4000000) == qword_1800411C0 )
  {
    v7[1] = 5;
    v11 = (__int16 *)off_1800411B0;
    v7[0] = 184549376;
    v8 = 0x4000000;
    v12 = *(unsigned __int16 *)off_1800411B0;
    v14 = byte_18003A901;
    v13 = 2;
    v15 = 42;
    v16 = 1;
    EtwEventWriteTransfer(qword_1800411C8, v7, 0, 0, 2, &v11);
  }
  v4 = (const struct CPenProcessInfo *)*((_QWORD *)this + 73);
  v10 = 1;
  v9 = 0;
  v5 = *((_DWORD *)v4 + 3) == 0;
  v6 = _mm_cvtsi128_si32(_mm_srli_si128((__m128i)0LL, 4));
  DWORD2(v9) = 1;
  if ( v5 )
    v6 = 1;
  DWORD1(v9) = v6;
  CServiceModule::StartPenProcessAsUser(this, v4, a2, (const struct CPenProcessStartInfo *)&v9);
  if ( WPP_GLOBAL_Control != (struct _GUID *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[1].Data4[4] & 0x10) != 0 )
    WPP_SF_s(
      *(_QWORD *)&WPP_GLOBAL_Control[1].Data1,
      122,
      WPP_689c0dbffb35351eabe1c9663a4c4c53_Traceguids,
      "PENSERVICE_CServiceModule::OnCtfmonRequest");
}

```

## disassembly

```asm
0x18000f260  mov     [rsp+arg_10], rbx
0x18000f265  push    rbp
0x18000f266  push    rsi
0x18000f267  push    rdi
0x18000f268  sub     rsp, 90h
0x18000f26f  mov     rax, cs:__security_cookie
0x18000f276  xor     rax, rsp
0x18000f279  mov     [rsp+0A8h+var_28], rax
0x18000f281  mov     rbx, rdx
0x18000f284  mov     rdi, rcx
0x18000f287  mov     rcx, cs:WPP_GLOBAL_Control
0x18000f28e  lea     rbp, WPP_GLOBAL_Control
0x18000f295  cmp     rcx, rbp
0x18000f298  jz      short loc_18000F2C3
0x18000f29a  test    byte ptr [rcx+1Ch], 10h
0x18000f29e  jz      short loc_18000F2C3
0x18000f2a0  mov     eax, [rbx+4]
0x18000f2a3  lea     r9, aPenserviceCser_0; "PENSERVICE_CServiceModule::OnCtfmonRequ"...
0x18000f2aa  mov     rcx, [rcx+10h]
0x18000f2ae  lea     r8, WPP_689c0dbffb35351eabe1c9663a4c4c53_Traceguids
0x18000f2b5  mov     edx, 79h ; 'y'
0x18000f2ba  mov     [rsp+0A8h+var_88], eax
0x18000f2be  call    WPP_SF_sd
0x18000f2c3  mov     eax, cs:dword_1800411A8
0x18000f2c9  mov     esi, 1
0x18000f2ce  cmp     eax, 5
0x18000f2d1  jbe     loc_18000F392
0x18000f2d7  mov     rcx, cs:qword_1800411C0
0x18000f2de  mov     rax, cs:qword_1800411B8
0x18000f2e5  bt      rax, 1Ah
0x18000f2ea  jnb     loc_18000F392
0x18000f2f0  mov     rax, rcx
0x18000f2f3  and     eax, 4000000h
0x18000f2f8  cmp     rax, rcx
0x18000f2fb  jnz     loc_18000F392
0x18000f301  movzx   eax, cs:word_18003A8F7
0x18000f308  lea     rcx, _TraceLoggingMetadata
0x18000f30f  mov     [rsp+0A8h+var_6C], eax
0x18000f313  lea     rdx, [rsp+0A8h+var_70]
0x18000f318  mov     rax, cs:off_1800411B0
0x18000f31f  xor     r9d, r9d
0x18000f322  mov     [rsp+0A8h+var_48], rax
0x18000f327  xor     r8d, r8d
0x18000f32a  mov     [rsp+0A8h+var_70], 0B000000h
0x18000f332  mov     [rsp+0A8h+var_68], 4000000h
0x18000f33b  movzx   eax, word ptr [rax]
0x18000f33e  mov     [rsp+0A8h+var_40], eax
0x18000f342  lea     rax, byte_18003A901
0x18000f349  mov     [rsp+0A8h+var_38], rax
0x18000f34e  lea     rax, _TraceLoggingMetadataEnd
0x18000f355  sub     eax, ecx
0x18000f357  mov     [rsp+0A8h+var_3C], 2
0x18000f35f  mov     [rsp+0A8h+var_30], 2Ah ; '*'
0x18000f367  mov     [rsp+0A8h+var_2C], esi
0x18000f36b  mov     [rsp+0A8h+var_78], eax
0x18000f36f  mov     eax, [rsp+0A8h+var_78]
0x18000f373  mov     rcx, cs:qword_1800411C8
0x18000f37a  lea     rax, [rsp+0A8h+var_48]
0x18000f37f  mov     [rsp+0A8h+var_80], rax
0x18000f384  mov     [rsp+0A8h+var_88], 2
0x18000f38c  call    cs:__imp_EtwEventWriteTransfer
0x18000f392  mov     rdx, [rdi+248h]; struct CPenProcessInfo *
0x18000f399  lea     r9, [rsp+0A8h+var_60]; struct CPenProcessStartInfo *
0x18000f39e  xorps   xmm0, xmm0
0x18000f3a1  mov     [rsp+0A8h+var_50], rsi
0x18000f3a6  movdqu  [rsp+0A8h+var_60], xmm0
0x18000f3ac  mov     r8, rbx; struct CPenSession *
0x18000f3af  mov     rcx, rdi; Context
0x18000f3b2  psrldq  xmm0, 4
0x18000f3b7  cmp     dword ptr [rdx+0Ch], 0
0x18000f3bb  movd    eax, xmm0
0x18000f3bf  mov     dword ptr [rsp+0A8h+var_60+8], esi
0x18000f3c3  cmovz   eax, esi
0x18000f3c6  mov     dword ptr [rsp+0A8h+var_60+4], eax
0x18000f3ca  call    ?StartPenProcessAsUser@CServiceModule@@QEAAXPEBVCPenProcessInfo@@PEAVCPenSession@@PEBUCPenProcessStartInfo@@@Z; CServiceModule::StartPenProcessAsUser(CPenProcessInfo const *,CPenSession *,CPenProcessStartInfo const *)
0x18000f3cf  mov     rcx, cs:WPP_GLOBAL_Control
0x18000f3d6  cmp     rcx, rbp
0x18000f3d9  jz      short loc_18000F3FD
0x18000f3db  test    byte ptr [rcx+1Ch], 10h
0x18000f3df  jz      short loc_18000F3FD
0x18000f3e1  mov     rcx, [rcx+10h]
0x18000f3e5  lea     r9, aPenserviceCser_0; "PENSERVICE_CServiceModule::OnCtfmonRequ"...
0x18000f3ec  mov     edx, 7Ah ; 'z'
0x18000f3f1  lea     r8, WPP_689c0dbffb35351eabe1c9663a4c4c53_Traceguids
0x18000f3f8  call    WPP_SF_s
0x18000f3fd  mov     rcx, [rsp+0A8h+var_28]
0x18000f405  xor     rcx, rsp; StackCookie
0x18000f408  call    __security_check_cookie
0x18000f40d  mov     rbx, [rsp+0A8h+arg_10]
0x18000f415  add     rsp, 90h
0x18000f41c  pop     rdi
0x18000f41d  pop     rsi
0x18000f41e  pop     rbp
0x18000f41f  retn
```
