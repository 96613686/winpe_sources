# SrvOdbLaunchBackgroundTask

- ea: `0x180069bb0`
- end: `0x18006a003`
- name: `SrvOdbLaunchBackgroundTask`
- size: `1107`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `authz_impersonation, loader_planting, service_task`

## callees

- `0x18002823c`
- `0x180069bb0`
- `0x1800946a0`

## import_xrefs

- `ntdll!RtlValidSid` at `0x180069d26`
- `ntdll!RtlValidSid` at `0x180069d26`
- `ntdll!RtlLengthSid` at `0x180069d15`
- `ntdll!RtlLengthSid` at `0x180069d15`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180069cf2`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180069fd1`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180069cf2`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180069fd1`

## pseudocode

```c
__int64 __fastcall SrvOdbLaunchBackgroundTask(
        void *a1,
        unsigned int a2,
        unsigned __int8 *a3,
        unsigned int a4,
        void *a5,
        unsigned int a6,
        unsigned __int16 *a7,
        unsigned __int16 *a8,
        struct _GUID *a9,
        unsigned __int8 *a10,
        int a11,
        struct _OdbLaunchInfo *a12,
        struct _GUID *a13,
        struct _GUID *a14)
{
  __int64 *v14; // rsi
  __int64 *v15; // rdi
  int v18; // ebx
  __int64 *v19; // rdx
  __int64 v20; // rax
  __int64 v21; // rcx
  bool v22; // zf
  int v23; // ecx
  int v24; // eax
  int v25; // eax
  int v26; // eax
  size_t size; // [rsp+50h] [rbp-B0h]
  unsigned int v29; // [rsp+70h] [rbp-90h] BYREF
  unsigned int v30; // [rsp+74h] [rbp-8Ch] BYREF
  PSID Sid; // [rsp+78h] [rbp-88h]
  struct _OdbLaunchInfo *v32; // [rsp+80h] [rbp-80h] BYREF
  EVENT_DESCRIPTOR EventDescriptor; // [rsp+88h] [rbp-78h] BYREF
  unsigned __int8 *v34; // [rsp+98h] [rbp-68h]
  RPC_BINDING_HANDLE Binding; // [rsp+A0h] [rbp-60h]
  GUID v36; // [rsp+A8h] [rbp-58h] BYREF
  GUID v37; // [rsp+B8h] [rbp-48h] BYREF
  struct _EVENT_DATA_DESCRIPTOR UserData; // [rsp+C8h] [rbp-38h] BYREF
  char *v39; // [rsp+D8h] [rbp-28h]
  int v40; // [rsp+E0h] [rbp-20h]
  int v41; // [rsp+E4h] [rbp-1Ch]
  struct _EVENT_DATA_DESCRIPTOR v42; // [rsp+F0h] [rbp-10h] BYREF
  char *v43; // [rsp+100h] [rbp+0h]
  int v44; // [rsp+108h] [rbp+8h]
  int v45; // [rsp+10Ch] [rbp+Ch]
  const unsigned __int16 *v46; // [rsp+110h] [rbp+10h]
  __int64 v47; // [rsp+118h] [rbp+18h]
  GUID *v48; // [rsp+120h] [rbp+20h]
  __int64 v49; // [rsp+128h] [rbp+28h]
  GUID *v50; // [rsp+130h] [rbp+30h]
  __int64 v51; // [rsp+138h] [rbp+38h]
  struct _OdbLaunchInfo **v52; // [rsp+140h] [rbp+40h]
  __int64 v53; // [rsp+148h] [rbp+48h]
  unsigned __int8 *v54; // [rsp+150h] [rbp+50h]
  int v55; // [rsp+158h] [rbp+58h]
  int v56; // [rsp+15Ch] [rbp+5Ch]
  __int64 *v57; // [rsp+160h] [rbp+60h]
  int v58; // [rsp+168h] [rbp+68h]
  int v59; // [rsp+16Ch] [rbp+6Ch]
  unsigned int *v60; // [rsp+170h] [rbp+70h]
  __int64 v61; // [rsp+178h] [rbp+78h]
  unsigned int *v62; // [rsp+180h] [rbp+80h]
  __int64 v63; // [rsp+188h] [rbp+88h]
  __int64 *v64; // [rsp+190h] [rbp+90h]
  int v65; // [rsp+198h] [rbp+98h]
  int v66; // [rsp+19Ch] [rbp+9Ch]
  __int64 *v67; // [rsp+1A0h] [rbp+A0h]
  int v68; // [rsp+1A8h] [rbp+A8h]
  int v69; // [rsp+1ACh] [rbp+ACh]

  v14 = (__int64 *)a7;
  v15 = (__int64 *)a8;
  Sid = a5;
  v34 = a10;
  v32 = a12;
  v30 = a4;
  Binding = a1;
  v37 = 0;
  v36 = 0;
  if ( (unsigned int)dword_1800C3098 > 5 && (qword_1800C30A8 & 8) != 0 && (qword_1800C30B0 & 8) == qword_1800C30B0 )
  {
    *(_DWORD *)&EventDescriptor.Level = 261;
    UserData.Ptr = (ULONGLONG)off_1800C30A0;
    *(_DWORD *)&EventDescriptor.Id = 184549376;
    EventDescriptor.Keyword = 8;
    UserData.Size = *(unsigned __int16 *)off_1800C30A0;
    v39 = byte_1800B7C65;
    UserData.Reserved = 2;
    v40 = 26;
    v41 = 1;
    v29 = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
    EventWriteTransfer(RegHandle, &EventDescriptor, 0, 0, 2u, &UserData);
  }
  if ( a2 >= 0xC && a2 == RtlLengthSid(a3) && RtlValidSid(a3) )
  {
    LODWORD(size) = a11;
    v18 = SrvOdbLaunchBackgroundTaskInternal(Binding, a3, Sid, v30, 0, a6, a7, a8, a9, v34, size, v32, a13, a14);
    if ( v18 >= 0 )
      v18 = 0;
  }
  else
  {
    a3 = (unsigned __int8 *)&BipTraceLoggingNullSid;
    v18 = -805306129;
  }
  v37 = GUID_NULL;
  if ( a14 )
    v37 = *a14;
  v36 = GUID_NULL;
  if ( a13 )
    v36 = *a13;
  v19 = (__int64 *)Sid;
  if ( !Sid )
    v19 = &BipTraceLoggingNullSid;
  if ( (unsigned int)dword_1800C3098 > 4 && (qword_1800C30A8 & 9) != 0 && (qword_1800C30B0 & 9) == qword_1800C30B0 )
  {
    v30 = a6;
    v20 = -1;
    v29 = 0;
    LODWORD(v32) = v18;
    if ( a8 )
    {
      v21 = -1;
      do
        v22 = a8[++v21] == 0;
      while ( !v22 );
      v23 = 2 * v21 + 2;
    }
    else
    {
      v15 = &qword_1800A1670;
      v23 = 2;
    }
    v67 = v15;
    v68 = v23;
    v69 = 0;
    if ( a7 )
    {
      do
        v22 = a7[++v20] == 0;
      while ( !v22 );
      v24 = 2 * v20 + 2;
    }
    else
    {
      v14 = &qword_1800A1670;
      v24 = 2;
    }
    v65 = v24;
    v66 = 0;
    v62 = &v30;
    v64 = v14;
    v60 = &v29;
    v63 = 4;
    v61 = 4;
    v25 = *((unsigned __int8 *)v19 + 1);
    v57 = v19;
    v59 = 0;
    *(_DWORD *)&EventDescriptor.Id = 184549376;
    EventDescriptor.Keyword = 9;
    v58 = 4 * v25 + 8;
    v26 = a3[1];
    v56 = 0;
    v54 = a3;
    v53 = 4;
    v51 = 16;
    v55 = 4 * v26 + 8;
    v52 = &v32;
    v50 = &v36;
    v48 = &v37;
    v46 = &qword_1800A1850;
    *(_DWORD *)&EventDescriptor.Level = 516;
    v42.Ptr = (ULONGLONG)off_1800C30A0;
    v49 = 16;
    v47 = 1;
    v42.Size = *(unsigned __int16 *)off_1800C30A0;
    v43 = byte_1800B7C8B;
    v42.Reserved = 2;
    v44 = 128;
    v45 = 1;
    LODWORD(Sid) = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
    EventWriteTransfer(RegHandle, &EventDescriptor, 0, 0, 0xCu, &v42);
  }
  return (unsigned int)v18;
}

```

## disassembly

```asm
0x180069bb0  mov     [rsp-8+arg_8], rbx
0x180069bb5  push    rbp
0x180069bb6  push    rsi
0x180069bb7  push    rdi
0x180069bb8  push    r12
0x180069bba  push    r13
0x180069bbc  push    r14
0x180069bbe  push    r15
0x180069bc0  lea     rbp, [rsp-0C0h]
0x180069bc8  sub     rsp, 1C0h
0x180069bcf  mov     rax, cs:__security_cookie
0x180069bd6  xor     rax, rsp
0x180069bd9  mov     [rbp+0F0h+var_40], rax
0x180069be0  mov     rax, [rbp+0F0h+arg_20]
0x180069be7  xorps   xmm0, xmm0
0x180069bea  mov     rsi, [rbp+0F0h+arg_30]
0x180069bf1  xorps   xmm1, xmm1
0x180069bf4  mov     rdi, [rbp+0F0h+arg_38]
0x180069bfb  mov     ebx, edx
0x180069bfd  mov     r15, [rbp+0F0h+arg_60]
0x180069c04  lea     rdx, _TraceLoggingMetadata
0x180069c0b  mov     r14, [rbp+0F0h+arg_68]
0x180069c12  mov     r13, r8
0x180069c15  mov     [rsp+1F0h+Sid], rax
0x180069c1a  mov     rax, [rbp+0F0h+arg_48]
0x180069c21  mov     [rbp+0F0h+var_158], rax
0x180069c25  mov     rax, [rbp+0F0h+arg_58]
0x180069c2c  mov     [rbp+0F0h+var_170], rax
0x180069c30  mov     eax, cs:dword_1800C3098
0x180069c36  mov     [rsp+1F0h+var_17C], r9d
0x180069c3b  mov     [rbp+0F0h+Binding], rcx
0x180069c3f  movups  [rbp+0F0h+var_138], xmm0
0x180069c43  movups  [rbp+0F0h+var_148], xmm1
0x180069c47  cmp     eax, 5
0x180069c4a  jbe     loc_180069CF8
0x180069c50  mov     rcx, cs:qword_1800C30B0
0x180069c57  mov     rax, cs:qword_1800C30A8
0x180069c5e  test    al, 8
0x180069c60  jz      loc_180069CF8
0x180069c66  mov     rax, rcx
0x180069c69  and     eax, 8
0x180069c6c  cmp     rax, rcx
0x180069c6f  jnz     loc_180069CF8
0x180069c75  movzx   eax, cs:word_1800B7C5B
0x180069c7c  xor     r9d, r9d; RelatedActivityId
0x180069c7f  mov     dword ptr [rbp+0F0h+EventDescriptor.Level], eax
0x180069c82  xor     r8d, r8d; ActivityId
0x180069c85  mov     rax, cs:off_1800C30A0
0x180069c8c  mov     [rbp+0F0h+var_128.Ptr], rax
0x180069c90  mov     dword ptr [rbp+0F0h+EventDescriptor.Id], 0B000000h
0x180069c97  mov     [rbp+0F0h+EventDescriptor.Keyword], 8
0x180069c9f  movzx   eax, word ptr [rax]
0x180069ca2  mov     [rbp+0F0h+var_128.Size], eax
0x180069ca5  lea     rax, byte_1800B7C65
0x180069cac  mov     [rbp+0F0h+var_118], rax
0x180069cb0  lea     rax, _TraceLoggingMetadataEnd
0x180069cb7  sub     eax, edx
0x180069cb9  mov     dword ptr [rbp+0F0h+var_128.0Ch], 2
0x180069cc0  mov     [rbp+0F0h+var_110], 1Ah
0x180069cc7  lea     rdx, [rbp+0F0h+EventDescriptor]; EventDescriptor
0x180069ccb  mov     [rbp+0F0h+var_10C], 1
0x180069cd2  mov     [rsp+1F0h+var_180], eax
0x180069cd6  mov     eax, [rsp+1F0h+var_180]
0x180069cda  mov     rcx, cs:RegHandle; RegHandle
0x180069ce1  lea     rax, [rbp+0F0h+var_128]
0x180069ce5  mov     [rsp+1F0h+UserData], rax; UserData
0x180069cea  mov     [rsp+1F0h+UserDataCount], 2; UserDataCount
0x180069cf2  call    cs:__imp_EventWriteTransfer
0x180069cf8  mov     r12d, [rbp+0F0h+arg_28]
0x180069cff  lea     rax, BipTraceLoggingNullSid
0x180069d06  xor     r8d, r8d
0x180069d09  cmp     ebx, 0Ch
0x180069d0c  jb      loc_180069DAD
0x180069d12  mov     rcx, r13; Sid
0x180069d15  call    cs:__imp_RtlLengthSid
0x180069d1b  cmp     ebx, eax
0x180069d1d  jnz     loc_180069DA3
0x180069d23  mov     rcx, r13; Sid
0x180069d26  call    cs:__imp_RtlValidSid
0x180069d2c  test    al, al
0x180069d2e  jz      short loc_180069DA3
0x180069d30  mov     rax, [rbp+0F0h+var_170]
0x180069d34  mov     rdx, r13; pSid
0x180069d37  mov     r9d, [rsp+1F0h+var_17C]; unsigned int
0x180069d3c  mov     r8, [rsp+1F0h+Sid]; Sid
0x180069d41  mov     rcx, [rbp+0F0h+Binding]; Binding
0x180069d45  mov     [rsp+1F0h+var_188], r14; struct _GUID *
0x180069d4a  mov     [rsp+1F0h+var_190], r15; struct _GUID *
0x180069d4f  mov     [rsp+1F0h+var_198], rax; struct _OdbLaunchInfo *
0x180069d54  mov     eax, dword ptr [rbp+0F0h+arg_50]
0x180069d5a  mov     dword ptr [rsp+1F0h+size], eax; size
0x180069d5e  mov     rax, [rbp+0F0h+var_158]
0x180069d62  mov     [rsp+1F0h+var_1A8], rax; unsigned __int8 *
0x180069d67  mov     rax, [rbp+0F0h+arg_40]
0x180069d6e  mov     [rsp+1F0h+var_1B0], rax; struct _GUID *
0x180069d73  mov     [rsp+1F0h+var_1B8], rdi; unsigned __int16 *
0x180069d78  mov     [rsp+1F0h+var_1C0], rsi; unsigned __int16 *
0x180069d7d  mov     dword ptr [rsp+1F0h+UserData], r12d; unsigned int
0x180069d82  mov     [rsp+1F0h+UserDataCount], 0; unsigned int
0x180069d8a  call    ?SrvOdbLaunchBackgroundTaskInternal@@YAJPEAX0PEBEKKKPEBG2PEAU_GUID@@PEAEKPEAU_OdbLaunchInfo@@33@Z; SrvOdbLaunchBackgroundTaskInternal(void *,void *,uchar const *,ulong,ulong,ulong,ushort const *,ushort const *,_GUID *,uchar *,ulong,_OdbLaunchInfo *,_GUID *,_GUID *)
0x180069d8f  xor     r8d, r8d
0x180069d92  mov     ebx, eax
0x180069d94  test    eax, eax
0x180069d96  lea     rax, BipTraceLoggingNullSid
0x180069d9d  cmovns  ebx, r8d
0x180069da1  jmp     short loc_180069DB5
0x180069da3  lea     rax, BipTraceLoggingNullSid
0x180069daa  xor     r8d, r8d
0x180069dad  mov     r13, rax
0x180069db0  mov     ebx, 0D00000EFh
0x180069db5  movups  xmm1, xmmword ptr cs:GUID_NULL.Data1
0x180069dbc  movups  [rbp+0F0h+var_138], xmm1
0x180069dc0  test    r14, r14
0x180069dc3  jz      short loc_180069DCD
0x180069dc5  movups  xmm0, xmmword ptr [r14]
0x180069dc9  movups  [rbp+0F0h+var_138], xmm0
0x180069dcd  movups  [rbp+0F0h+var_148], xmm1
0x180069dd1  test    r15, r15
0x180069dd4  jz      short loc_180069DDE
0x180069dd6  movups  xmm0, xmmword ptr [r15]
0x180069dda  movups  [rbp+0F0h+var_148], xmm0
0x180069dde  mov     rdx, [rsp+1F0h+Sid]
0x180069de3  test    rdx, rdx
0x180069de6  cmovz   rdx, rax
0x180069dea  mov     eax, cs:dword_1800C3098
0x180069df0  cmp     eax, 4
0x180069df3  jbe     loc_180069FD7
0x180069df9  mov     rcx, cs:qword_1800C30B0
0x180069e00  mov     rax, cs:qword_1800C30A8
0x180069e07  test    al, 9
0x180069e09  jz      loc_180069FD7
0x180069e0f  mov     rax, rcx
0x180069e12  and     eax, 9
0x180069e15  cmp     rax, rcx
0x180069e18  jnz     loc_180069FD7
0x180069e1e  mov     [rsp+1F0h+var_17C], r12d
0x180069e23  mov     rax, 0FFFFFFFFFFFFFFFFh
0x180069e2a  mov     [rsp+1F0h+var_180], r8d
0x180069e2f  mov     dword ptr [rbp+0F0h+var_170], ebx
0x180069e32  test    rdi, rdi
0x180069e35  jz      short loc_180069E55
0x180069e37  mov     rcx, rax
0x180069e3a  nop     word ptr [rax+rax+00h]
0x180069e40  cmp     word ptr [rdi+rcx*2+2], 0
0x180069e46  lea     rcx, [rcx+1]
0x180069e4a  jnz     short loc_180069E40
0x180069e4c  lea     ecx, ds:2[rcx*2]
0x180069e53  jmp     short loc_180069E61
0x180069e55  lea     rdi, qword_1800A1670
0x180069e5c  mov     ecx, 2
0x180069e61  mov     [rbp+0F0h+var_50], rdi
0x180069e68  mov     [rbp+0F0h+var_48], ecx
0x180069e6e  mov     [rbp+0F0h+var_44], r8d
0x180069e75  test    rsi, rsi
0x180069e78  jz      short loc_180069E95
0x180069e7a  nop     word ptr [rax+rax+00h]
0x180069e80  cmp     word ptr [rsi+rax*2+2], 0
0x180069e86  lea     rax, [rax+1]
0x180069e8a  jnz     short loc_180069E80
0x180069e8c  lea     eax, ds:2[rax*2]
0x180069e93  jmp     short loc_180069EA1
0x180069e95  lea     rsi, qword_1800A1670
0x180069e9c  mov     eax, 2
0x180069ea1  mov     [rbp+0F0h+var_58], eax
0x180069ea7  lea     rcx, _TraceLoggingMetadata
0x180069eae  mov     [rbp+0F0h+var_54], r8d
0x180069eb5  lea     rax, [rsp+1F0h+var_17C]
0x180069eba  mov     [rbp+0F0h+var_70], rax
0x180069ec1  xor     r9d, r9d; RelatedActivityId
0x180069ec4  mov     [rbp+0F0h+var_60], rsi
0x180069ecb  lea     rax, [rsp+1F0h+var_180]
0x180069ed0  mov     [rbp+0F0h+var_80], rax
0x180069ed4  mov     [rbp+0F0h+var_68], 4
0x180069edf  mov     [rbp+0F0h+var_78], 4
0x180069ee7  movzx   eax, byte ptr [rdx+1]
0x180069eeb  mov     [rbp+0F0h+var_90], rdx
0x180069eef  lea     rdx, [rbp+0F0h+EventDescriptor]; EventDescriptor
0x180069ef3  mov     [rbp+0F0h+var_84], r8d
0x180069ef7  mov     dword ptr [rbp+0F0h+EventDescriptor.Id], 0B000000h
0x180069efe  lea     eax, ds:8[rax*4]
0x180069f05  mov     [rbp+0F0h+EventDescriptor.Keyword], 9
0x180069f0d  mov     [rbp+0F0h+var_88], eax
0x180069f10  movzx   eax, byte ptr [r13+1]
0x180069f15  mov     [rbp+0F0h+var_94], r8d
0x180069f19  xor     r8d, r8d; ActivityId
0x180069f1c  mov     [rbp+0F0h+var_A0], r13
0x180069f20  mov     [rbp+0F0h+var_A8], 4
0x180069f28  lea     eax, ds:8[rax*4]
0x180069f2f  mov     [rbp+0F0h+var_B8], 10h
0x180069f37  mov     [rbp+0F0h+var_98], eax
0x180069f3a  lea     rax, [rbp+0F0h+var_170]
0x180069f3e  mov     [rbp+0F0h+var_B0], rax
0x180069f42  lea     rax, [rbp+0F0h+var_148]
0x180069f46  mov     [rbp+0F0h+var_C0], rax
0x180069f4a  lea     rax, [rbp+0F0h+var_138]
0x180069f4e  mov     [rbp+0F0h+var_D0], rax
0x180069f52  lea     rax, qword_1800A1850
0x180069f59  mov     [rbp+0F0h+var_E0], rax
0x180069f5d  movzx   eax, cs:word_1800B7C81
0x180069f64  mov     dword ptr [rbp+0F0h+EventDescriptor.Level], eax
0x180069f67  mov     rax, cs:off_1800C30A0
0x180069f6e  mov     [rbp+0F0h+var_100.Ptr], rax
0x180069f72  mov     [rbp+0F0h+var_C8], 10h
0x180069f7a  mov     [rbp+0F0h+var_D8], 1
0x180069f82  movzx   eax, word ptr [rax]
0x180069f85  mov     [rbp+0F0h+var_100.Size], eax
0x180069f88  lea     rax, byte_1800B7C8B
0x180069f8f  mov     [rbp+0F0h+var_F0], rax
0x180069f93  lea     rax, _TraceLoggingMetadataEnd
0x180069f9a  sub     eax, ecx
0x180069f9c  mov     dword ptr [rbp+0F0h+var_100.0Ch], 2
0x180069fa3  mov     [rbp+0F0h+var_E8], 80h
0x180069faa  mov     [rbp+0F0h+var_E4], 1
0x180069fb1  mov     dword ptr [rsp+1F0h+Sid], eax
0x180069fb5  lea     rax, [rbp+0F0h+var_100]
0x180069fb9  mov     ecx, dword ptr [rsp+1F0h+Sid]
0x180069fbd  mov     rcx, cs:RegHandle; RegHandle
0x180069fc4  mov     [rsp+1F0h+UserData], rax; UserData
0x180069fc9  mov     [rsp+1F0h+UserDataCount], 0Ch; UserDataCount
0x180069fd1  call    cs:__imp_EventWriteTransfer
0x180069fd7  mov     eax, ebx
0x180069fd9  mov     rcx, [rbp+0F0h+var_40]
0x180069fe0  xor     rcx, rsp; StackCookie
0x180069fe3  call    __security_check_cookie
0x180069fe8  mov     rbx, [rsp+1F0h+arg_8]
0x180069ff0  add     rsp, 1C0h
0x180069ff7  pop     r15
0x180069ff9  pop     r14
0x180069ffb  pop     r13
0x180069ffd  pop     r12
0x180069fff  pop     rdi
0x18006a000  pop     rsi
0x18006a001  pop     rbp
0x18006a002  retn
```
