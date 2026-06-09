# WnfEventCallback

- ea: `0x1800038c0`
- end: `0x180003c8e`
- name: `WnfEventCallback`
- size: `974`
- prototype: `__int64 __fastcall(__int64, _QWORD *, unsigned int, unsigned int *, unsigned int)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x180003880`

## callees

- `0x1800038c0`
- `0x180005cc0`
- `0x1800069d0`
- `0x1800072e0`

## import_xrefs

- `ntdll!RtlReleaseSRWLockExclusive` at `0x1800039f5`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x1800039f5`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x1800039bb`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x1800039bb`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x1800039a3`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180003c56`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x1800039a3`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180003c56`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800039c1`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800039c1`

## pseudocode

```c
__int64 __fastcall WnfEventCallback(__int64 a1, _QWORD *a2, unsigned int a3, unsigned int *a4, unsigned int a5)
{
  int v9; // r13d
  unsigned __int8 v10; // si
  unsigned __int8 v11; // di
  int v12; // ecx
  int v13; // ebx
  unsigned int v14; // r8d
  __int64 v15; // rbx
  unsigned int v16; // r9d
  int v17; // edx
  int v18; // r10d
  unsigned int v19; // eax
  int v20; // r11d
  __int64 result; // rax
  unsigned int v22; // [rsp+40h] [rbp-C0h] BYREF
  int v23; // [rsp+44h] [rbp-BCh] BYREF
  int v24; // [rsp+48h] [rbp-B8h] BYREF
  int v25; // [rsp+4Ch] [rbp-B4h] BYREF
  int v26; // [rsp+50h] [rbp-B0h] BYREF
  int v27; // [rsp+54h] [rbp-ACh] BYREF
  __int64 v28; // [rsp+58h] [rbp-A8h] BYREF
  EVENT_DESCRIPTOR EventDescriptor; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v30; // [rsp+70h] [rbp-90h] BYREF
  EVENT_DESCRIPTOR v31; // [rsp+78h] [rbp-88h] BYREF
  struct _EVENT_DATA_DESCRIPTOR UserData; // [rsp+88h] [rbp-78h] BYREF
  char *v33; // [rsp+98h] [rbp-68h]
  int v34; // [rsp+A0h] [rbp-60h]
  int v35; // [rsp+A4h] [rbp-5Ch]
  __int64 *v36; // [rsp+A8h] [rbp-58h]
  __int64 v37; // [rsp+B0h] [rbp-50h]
  struct _EVENT_DATA_DESCRIPTOR v38; // [rsp+C0h] [rbp-40h] BYREF
  void *v39; // [rsp+D0h] [rbp-30h]
  int v40; // [rsp+D8h] [rbp-28h]
  int v41; // [rsp+DCh] [rbp-24h]
  __int64 *v42; // [rsp+E0h] [rbp-20h]
  __int64 v43; // [rsp+E8h] [rbp-18h]
  EVENT_DESCRIPTOR *p_EventDescriptor; // [rsp+F0h] [rbp-10h]
  __int64 v45; // [rsp+F8h] [rbp-8h]
  unsigned int *v46; // [rsp+100h] [rbp+0h]
  __int64 v47; // [rsp+108h] [rbp+8h]
  int *v48; // [rsp+110h] [rbp+10h]
  __int64 v49; // [rsp+118h] [rbp+18h]
  int *v50; // [rsp+120h] [rbp+20h]
  __int64 v51; // [rsp+128h] [rbp+28h]
  int *v52; // [rsp+130h] [rbp+30h]
  __int64 v53; // [rsp+138h] [rbp+38h]
  int *v54; // [rsp+140h] [rbp+40h]
  __int64 v55; // [rsp+148h] [rbp+48h]
  int *v56; // [rsp+150h] [rbp+50h]
  __int64 v57; // [rsp+158h] [rbp+58h]

  if ( (unsigned int)dword_180012000 > 4 )
  {
    v28 = a1;
    v36 = &v28;
    *(_DWORD *)&EventDescriptor.Level = 260;
    UserData.Ptr = (ULONGLONG)off_180012008;
    v37 = 8;
    *(_DWORD *)&EventDescriptor.Id = 184549376;
    EventDescriptor.Keyword = 0;
    UserData.Size = *(unsigned __int16 *)off_180012008;
    v33 = byte_18000F4A9;
    UserData.Reserved = 2;
    v34 = 35;
    v35 = 1;
    v22 = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
    EventWriteTransfer(RegHandle, &EventDescriptor, 0, 0, 3u, &UserData);
  }
  v9 = 0;
  v10 = 0;
  v11 = 0;
  if ( a3 )
  {
    if ( a5 < 8 )
    {
      v12 = 16;
      v13 = -1073741789;
      goto LABEL_21;
    }
    v14 = *a4;
    if ( a5 < (unsigned __int64)((*a4 >> 2) & 0xFFF) + 8 )
    {
      v12 = 32;
      v13 = -1073739509;
      goto LABEL_21;
    }
    v15 = (__int64)(a4 + 2);
    v16 = (v14 >> 2) & 0xFFF;
    if ( !v16 )
      v15 = 0;
    v17 = (v14 & 0x1000000) != 0 ? 2 : 0;
    v18 = (v14 & 0x1000000) != 0 ? 0x10 : 0;
    if ( (v14 & 0x800000) != 0 )
    {
      v18 += 16;
      v17 |= 1u;
    }
    v19 = v18 + 8;
    v20 = v17 | 4;
    if ( (v14 & 0x2000000) == 0 )
    {
      v19 = v18;
      v20 = v17;
    }
    if ( v16 < v19 )
    {
      v12 = 48;
      v13 = -1073741762;
      goto LABEL_21;
    }
    v9 = (v14 >> 2) & 0xFFF;
    v10 = v14 & 1;
    v11 = (v14 & 2) != 0;
    v13 = EaiProcessNotification(a1, (__int64)a2, !(v14 & 1), v11, v15, v16, v20, 0);
    if ( v13 < 0 )
    {
      v12 = 272;
      goto LABEL_21;
    }
    v12 = 0;
  }
  else
  {
    RtlAcquireSRWLockExclusive(a1 + 80);
    *(_DWORD *)(a1 + 88) = GetCurrentThreadId();
    EaiSignalCallback(3, a1, (_DWORD)a2, 0, 0, 0, 0);
    *(_DWORD *)(a1 + 88) = 0;
    RtlReleaseSRWLockExclusive(a1 + 80);
    v12 = 256;
  }
  v13 = 0;
LABEL_21:
  if ( (unsigned int)dword_180012000 > 4 )
  {
    v27 = v12;
    v42 = &v30;
    *(_QWORD *)&EventDescriptor.Id = *a2;
    v31.Keyword = 0;
    p_EventDescriptor = &EventDescriptor;
    v30 = a1;
    v46 = &v22;
    v48 = &v23;
    v43 = 8;
    v45 = 8;
    v22 = a3;
    v47 = 4;
    v23 = v9;
    v49 = 4;
    v51 = 4;
    v53 = 4;
    v26 = v13;
    v55 = 4;
    v57 = 4;
    *(_DWORD *)&v31.Id = 184549376;
    v24 = v10;
    v50 = &v24;
    v25 = v11;
    v52 = &v25;
    v54 = &v26;
    v56 = &v27;
    *(_DWORD *)&v31.Level = 516;
    v38.Ptr = (ULONGLONG)off_180012008;
    v38.Size = *(unsigned __int16 *)off_180012008;
    v39 = &unk_18000F4D8;
    v38.Reserved = 2;
    v40 = 122;
    v41 = 1;
    LODWORD(v28) = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
    EventWriteTransfer(RegHandle, &v31, 0, 0, 0xAu, &v38);
  }
  result = 0;
  if ( v13 == -1073741801 )
    return 3221225495LL;
  return result;
}

```

## disassembly

```asm
0x1800038c0  mov     [rsp-8+arg_10], rbx
0x1800038c5  push    rbp
0x1800038c6  push    rsi
0x1800038c7  push    rdi
0x1800038c8  push    r12
0x1800038ca  push    r13
0x1800038cc  push    r14
0x1800038ce  push    r15
0x1800038d0  lea     rbp, [rsp-70h]
0x1800038d5  sub     rsp, 170h
0x1800038dc  mov     rax, cs:__security_cookie
0x1800038e3  xor     rax, rsp
0x1800038e6  mov     [rbp+0A0h+var_40], rax
0x1800038ea  mov     eax, cs:dword_180012000
0x1800038f0  mov     r14, rcx
0x1800038f3  lea     rcx, _TraceLoggingMetadata
0x1800038fa  mov     rbx, r9
0x1800038fd  mov     r12d, r8d
0x180003900  mov     r15, rdx
0x180003903  cmp     eax, 4
0x180003906  jbe     loc_1800039A9
0x18000390c  lea     rax, [rsp+1A0h+var_148]
0x180003911  mov     [rsp+1A0h+var_148], r14
0x180003916  mov     [rbp+0A0h+var_F8], rax
0x18000391a  lea     rdx, [rsp+1A0h+EventDescriptor]; EventDescriptor
0x18000391f  movzx   eax, cs:word_18000F49F
0x180003926  xor     r9d, r9d; RelatedActivityId
0x180003929  mov     dword ptr [rsp+1A0h+EventDescriptor.Level], eax
0x18000392d  xor     r8d, r8d; ActivityId
0x180003930  mov     rax, cs:off_180012008
0x180003937  mov     [rbp+0A0h+var_118.Ptr], rax
0x18000393b  mov     [rbp+0A0h+var_F0], 8
0x180003943  mov     dword ptr [rsp+1A0h+EventDescriptor.Id], 0B000000h
0x18000394b  mov     [rsp+1A0h+EventDescriptor.Keyword], 0
0x180003954  movzx   eax, word ptr [rax]
0x180003957  mov     [rbp+0A0h+var_118.Size], eax
0x18000395a  lea     rax, byte_18000F4A9
0x180003961  mov     [rbp+0A0h+var_108], rax
0x180003965  lea     rax, _TraceLoggingMetadataEnd
0x18000396c  sub     eax, ecx
0x18000396e  mov     dword ptr [rbp+0A0h+var_118.0Ch], 2
0x180003975  mov     [rbp+0A0h+var_100], 23h ; '#'
0x18000397c  mov     [rbp+0A0h+var_FC], 1
0x180003983  mov     [rsp+1A0h+var_160], eax
0x180003987  mov     eax, [rsp+1A0h+var_160]
0x18000398b  mov     rcx, cs:RegHandle; RegHandle
0x180003992  lea     rax, [rbp+0A0h+var_118]
0x180003996  mov     [rsp+1A0h+UserData], rax; UserData
0x18000399b  mov     [rsp+1A0h+UserDataCount], 3; UserDataCount
0x1800039a3  call    cs:__imp_EventWriteTransfer
0x1800039a9  xor     r13d, r13d
0x1800039ac  xor     sil, sil
0x1800039af  xor     dil, dil
0x1800039b2  test    r12d, r12d
0x1800039b5  jnz     short loc_180003A07
0x1800039b7  lea     rcx, [r14+50h]
0x1800039bb  call    cs:__imp_RtlAcquireSRWLockExclusive
0x1800039c1  call    cs:__imp_GetCurrentThreadId
0x1800039c7  mov     [r14+58h], eax
0x1800039cb  xor     r9d, r9d
0x1800039ce  xor     eax, eax
0x1800039d0  mov     r8, r15
0x1800039d3  mov     [rsp+1A0h+var_170], rax
0x1800039d8  mov     rdx, r14
0x1800039db  mov     dword ptr [rsp+1A0h+UserData], eax
0x1800039df  mov     ecx, 3
0x1800039e4  mov     [rsp+1A0h+UserDataCount], eax
0x1800039e8  call    EaiSignalCallback
0x1800039ed  lea     rcx, [r14+50h]
0x1800039f1  mov     [r14+58h], r13d
0x1800039f5  call    cs:__imp_RtlReleaseSRWLockExclusive
0x1800039fb  mov     ecx, 100h
0x180003a00  xor     edx, edx
0x180003a02  jmp     loc_180003B0B
0x180003a07  mov     eax, [rbp+0A0h+arg_20]
0x180003a0d  cmp     eax, 8
0x180003a10  jnb     short loc_180003A23
0x180003a12  mov     ecx, 10h
0x180003a17  mov     ebx, 0C0000023h
0x180003a1c  xor     edx, edx
0x180003a1e  jmp     loc_180003B0D
0x180003a23  mov     r8d, [rbx]
0x180003a26  mov     ecx, r8d
0x180003a29  shr     rcx, 2
0x180003a2d  and     ecx, 0FFFh
0x180003a33  add     rcx, 8
0x180003a37  cmp     rax, rcx
0x180003a3a  jnb     short loc_180003A4D
0x180003a3c  mov     ecx, 20h ; ' '
0x180003a41  mov     ebx, 0C000090Bh
0x180003a46  xor     edx, edx
0x180003a48  jmp     loc_180003B0D
0x180003a4d  xor     eax, eax
0x180003a4f  add     rbx, 8
0x180003a53  mov     r9d, r8d
0x180003a56  mov     ecx, r8d
0x180003a59  shr     r9d, 2
0x180003a5d  and     r9d, 0FFFh
0x180003a64  cmovz   rbx, rax
0x180003a68  and     ecx, 1000000h
0x180003a6e  mov     eax, ecx
0x180003a70  neg     eax
0x180003a72  sbb     edx, edx
0x180003a74  and     edx, 2
0x180003a77  neg     ecx
0x180003a79  sbb     r10d, r10d
0x180003a7c  and     r10d, 10h
0x180003a80  bt      r8d, 17h
0x180003a85  jnb     short loc_180003A8E
0x180003a87  add     r10d, 10h
0x180003a8b  or      edx, 1
0x180003a8e  mov     r11d, edx
0x180003a91  lea     eax, [r10+8]
0x180003a95  or      r11d, 4
0x180003a99  bt      r8d, 19h
0x180003a9e  cmovnb  eax, r10d
0x180003aa2  cmovnb  r11d, edx
0x180003aa6  cmp     r9d, eax
0x180003aa9  jnb     short loc_180003AB9
0x180003aab  mov     ecx, 30h ; '0'
0x180003ab0  mov     ebx, 0C000003Eh
0x180003ab5  xor     edx, edx
0x180003ab7  jmp     short loc_180003B0D
0x180003ab9  mov     esi, r8d
0x180003abc  mov     [rsp+1A0h+var_168], 0
0x180003ac5  mov     edi, r8d
0x180003ac8  mov     dword ptr [rsp+1A0h+var_170], r11d
0x180003acd  mov     dword ptr [rsp+1A0h+UserData], r9d
0x180003ad2  mov     r13d, r9d
0x180003ad5  and     esi, 1
0x180003ad8  shr     edi, 1
0x180003ada  movzx   r8d, sil
0x180003ade  mov     qword ptr [rsp+1A0h+UserDataCount], rbx
0x180003ae3  and     dil, 1
0x180003ae7  xor     r8b, 1
0x180003aeb  movzx   r9d, dil
0x180003aef  mov     rdx, r15
0x180003af2  mov     rcx, r14
0x180003af5  call    EaiProcessNotification
0x180003afa  xor     edx, edx
0x180003afc  mov     ebx, eax
0x180003afe  test    eax, eax
0x180003b00  jns     short loc_180003B09
0x180003b02  mov     ecx, 110h
0x180003b07  jmp     short loc_180003B0D
0x180003b09  mov     ecx, edx
0x180003b0b  mov     ebx, edx
0x180003b0d  mov     eax, cs:dword_180012000
0x180003b13  cmp     eax, 4
0x180003b16  jbe     loc_180003C5C
0x180003b1c  mov     [rsp+1A0h+var_14C], ecx
0x180003b20  lea     rax, [rsp+1A0h+var_130]
0x180003b25  mov     [rbp+0A0h+var_C0], rax
0x180003b29  lea     rcx, _TraceLoggingMetadata
0x180003b30  mov     rax, [r15]
0x180003b33  xor     r9d, r9d; RelatedActivityId
0x180003b36  mov     qword ptr [rsp+1A0h+EventDescriptor.Id], rax
0x180003b3b  xor     r8d, r8d; ActivityId
0x180003b3e  mov     [rbp+0A0h+var_128.Keyword], rdx
0x180003b42  lea     rax, [rsp+1A0h+EventDescriptor]
0x180003b47  mov     [rbp+0A0h+var_B0], rax
0x180003b4b  lea     rdx, [rsp+1A0h+var_128]; EventDescriptor
0x180003b50  mov     [rsp+1A0h+var_130], r14
0x180003b55  lea     rax, [rsp+1A0h+var_160]
0x180003b5a  mov     [rbp+0A0h+var_A0], rax
0x180003b5e  lea     rax, [rsp+1A0h+var_15C]
0x180003b63  mov     [rbp+0A0h+var_90], rax
0x180003b67  mov     [rbp+0A0h+var_B8], 8
0x180003b6f  mov     [rbp+0A0h+var_A8], 8
0x180003b77  mov     [rsp+1A0h+var_160], r12d
0x180003b7c  mov     [rbp+0A0h+var_98], 4
0x180003b84  mov     [rsp+1A0h+var_15C], r13d
0x180003b89  mov     [rbp+0A0h+var_88], 4
0x180003b91  mov     [rbp+0A0h+var_78], 4
0x180003b99  mov     [rbp+0A0h+var_68], 4
0x180003ba1  mov     [rsp+1A0h+var_150], ebx
0x180003ba5  mov     [rbp+0A0h+var_58], 4
0x180003bad  mov     [rbp+0A0h+var_48], 4
0x180003bb5  mov     dword ptr [rsp+1A0h+var_128.Id], 0B000000h
0x180003bbd  movzx   eax, sil
0x180003bc1  mov     [rsp+1A0h+var_158], eax
0x180003bc5  lea     rax, [rsp+1A0h+var_158]
0x180003bca  mov     [rbp+0A0h+var_80], rax
0x180003bce  movzx   eax, dil
0x180003bd2  mov     [rsp+1A0h+var_154], eax
0x180003bd6  lea     rax, [rsp+1A0h+var_154]
0x180003bdb  mov     [rbp+0A0h+var_70], rax
0x180003bdf  lea     rax, [rsp+1A0h+var_150]
0x180003be4  mov     [rbp+0A0h+var_60], rax
0x180003be8  lea     rax, [rsp+1A0h+var_14C]
0x180003bed  mov     [rbp+0A0h+var_50], rax
0x180003bf1  movzx   eax, cs:word_18000F4CE
0x180003bf8  mov     dword ptr [rsp+1A0h+var_128.Level], eax
0x180003bfc  mov     rax, cs:off_180012008
0x180003c03  mov     [rbp+0A0h+var_E0.Ptr], rax
0x180003c07  movzx   eax, word ptr [rax]
0x180003c0a  mov     [rbp+0A0h+var_E0.Size], eax
0x180003c0d  lea     rax, unk_18000F4D8
0x180003c14  mov     [rbp+0A0h+var_D0], rax
0x180003c18  lea     rax, _TraceLoggingMetadataEnd
0x180003c1f  sub     eax, ecx
0x180003c21  mov     dword ptr [rbp+0A0h+var_E0.0Ch], 2
0x180003c28  mov     [rbp+0A0h+var_C8], 7Ah ; 'z'
0x180003c2f  mov     [rbp+0A0h+var_C4], 1
0x180003c36  mov     dword ptr [rsp+1A0h+var_148], eax
0x180003c3a  mov     eax, dword ptr [rsp+1A0h+var_148]
0x180003c3e  mov     rcx, cs:RegHandle; RegHandle
0x180003c45  lea     rax, [rbp+0A0h+var_E0]
0x180003c49  mov     [rsp+1A0h+UserData], rax; UserData
0x180003c4e  mov     [rsp+1A0h+UserDataCount], 0Ah; UserDataCount
0x180003c56  call    cs:__imp_EventWriteTransfer
0x180003c5c  xor     eax, eax
0x180003c5e  cmp     ebx, 0C0000017h
0x180003c64  cmovz   eax, ebx
0x180003c67  mov     rcx, [rbp+0A0h+var_40]
0x180003c6b  xor     rcx, rsp; StackCookie
0x180003c6e  call    __security_check_cookie
0x180003c73  mov     rbx, [rsp+1A0h+arg_10]
0x180003c7b  add     rsp, 170h
0x180003c82  pop     r15
0x180003c84  pop     r14
0x180003c86  pop     r13
0x180003c88  pop     r12
0x180003c8a  pop     rdi
0x180003c8b  pop     rsi
0x180003c8c  pop     rbp
0x180003c8d  retn
```
