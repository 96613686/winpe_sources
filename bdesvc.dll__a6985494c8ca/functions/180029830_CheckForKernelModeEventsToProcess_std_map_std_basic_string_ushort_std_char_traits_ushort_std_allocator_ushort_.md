# CheckForKernelModeEventsToProcess(std::map<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,VolumeEntry,std::less<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>,std::allocator<std::pair<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const,VolumeEntry>>> *)

- ea: `0x180029830`
- end: `0x180029cf1`
- name: `?CheckForKernelModeEventsToProcess@@YAXPEAV?$map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UVolumeEntry@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UVolumeEntry@@@std@@@2@@std@@@Z`
- size: `1217`
- prototype: `void __fastcall(__int64 **)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x180007d90`

## callees

- `0x180009f30`
- `0x180024d40`
- `0x180027508`
- `0x180029830`
- `0x180034070`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180029b99`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180029c8b`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180029b99`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180029c8b`

## pseudocode

```c
void __fastcall CheckForKernelModeEventsToProcess(__int64 **a1)
{
  struct RecoveryTelemetery *Instance; // rdi
  PVOID *v3; // rcx
  __int64 *v4; // rcx
  __int64 **v5; // rdx
  __int64 *i; // rax
  __int64 *j; // rdx
  int v8; // eax
  __int16 v9; // ax
  __int128 v10; // xmm0
  int v11; // eax
  __int16 v12; // [rsp+30h] [rbp-D0h] BYREF
  unsigned int v13; // [rsp+34h] [rbp-CCh]
  int v14; // [rsp+38h] [rbp-C8h] BYREF
  __int64 v15; // [rsp+40h] [rbp-C0h] BYREF
  _QWORD v16[2]; // [rsp+48h] [rbp-B8h] BYREF
  __int16 v17; // [rsp+58h] [rbp-A8h] BYREF
  char *v18; // [rsp+60h] [rbp-A0h]
  __int16 v19; // [rsp+68h] [rbp-98h] BYREF
  char *v20; // [rsp+70h] [rbp-90h]
  __int16 v21; // [rsp+78h] [rbp-88h] BYREF
  char *v22; // [rsp+80h] [rbp-80h]
  __int16 v23; // [rsp+88h] [rbp-78h] BYREF
  char *v24; // [rsp+90h] [rbp-70h]
  __int16 v25; // [rsp+98h] [rbp-68h] BYREF
  __int128 v26; // [rsp+A0h] [rbp-60h] BYREF
  EVENT_DESCRIPTOR EventDescriptor; // [rsp+B0h] [rbp-50h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v28; // [rsp+C0h] [rbp-40h] BYREF
  char *v29; // [rsp+D0h] [rbp-30h]
  int v30; // [rsp+D8h] [rbp-28h]
  int v31; // [rsp+DCh] [rbp-24h]
  __int64 *v32; // [rsp+E0h] [rbp-20h]
  __int64 v33; // [rsp+E8h] [rbp-18h]
  struct _EVENT_DATA_DESCRIPTOR UserData; // [rsp+F0h] [rbp-10h] BYREF
  char *v35; // [rsp+100h] [rbp+0h]
  int v36; // [rsp+108h] [rbp+8h]
  int v37; // [rsp+10Ch] [rbp+Ch]
  __int128 *v38; // [rsp+110h] [rbp+10h]
  __int64 v39; // [rsp+118h] [rbp+18h]
  int *v40; // [rsp+120h] [rbp+20h]
  __int64 v41; // [rsp+128h] [rbp+28h]
  __int16 *v42; // [rsp+130h] [rbp+30h]
  __int64 v43; // [rsp+138h] [rbp+38h]
  __int64 *v44; // [rsp+140h] [rbp+40h]
  __int64 v45; // [rsp+148h] [rbp+48h]
  __int16 *v46; // [rsp+150h] [rbp+50h]
  __int64 v47; // [rsp+158h] [rbp+58h]
  char *v48; // [rsp+160h] [rbp+60h]
  __int64 v49; // [rsp+168h] [rbp+68h]
  __int16 *v50; // [rsp+170h] [rbp+70h]
  __int64 v51; // [rsp+178h] [rbp+78h]
  char *v52; // [rsp+180h] [rbp+80h]
  __int64 v53; // [rsp+188h] [rbp+88h]
  __int16 *v54; // [rsp+190h] [rbp+90h]
  __int64 v55; // [rsp+198h] [rbp+98h]
  char *v56; // [rsp+1A0h] [rbp+A0h]
  __int64 v57; // [rsp+1A8h] [rbp+A8h]
  __int16 *v58; // [rsp+1B0h] [rbp+B0h]
  __int64 v59; // [rsp+1B8h] [rbp+B8h]
  char *v60; // [rsp+1C0h] [rbp+C0h]
  __int64 v61; // [rsp+1C8h] [rbp+C8h]
  __int16 *v62; // [rsp+1D0h] [rbp+D0h]
  __int64 v63; // [rsp+1D8h] [rbp+D8h]
  char *v64; // [rsp+1E0h] [rbp+E0h]
  __int64 v65; // [rsp+1E8h] [rbp+E8h]
  _QWORD *v66; // [rsp+1F0h] [rbp+F0h]
  __int64 v67; // [rsp+1F8h] [rbp+F8h]

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 131, &WPP_87bbf11076dc3c61a5de4204d50ff79d_Traceguids);
  Instance = RecoveryTelemetery::getInstance();
  if ( a1 )
  {
    v4 = (__int64 *)**a1;
    while ( v4 != *a1 )
    {
      if ( *((_DWORD *)v4 + 22) && (v4[8] & 0x4000) != 0 )
      {
        v8 = *((_DWORD *)v4 + 16);
        if ( (v8 & 1) != 0 )
        {
          ProcessBootErrorLogLaunch(v4[10], 0);
          if ( Instance && *((_BYTE *)Instance + 16) )
          {
            if ( (unsigned int)dword_18009A348 > 4
              && (qword_18009A358 & 0x400000000000LL) != 0
              && (qword_18009A360 & 0x400000000000LL) == qword_18009A360 )
            {
              v9 = *((_WORD *)Instance + 10);
              v10 = *(_OWORD *)Instance;
              v16[1] = (char *)Instance + 88;
              v64 = (char *)Instance + 88;
              v12 = v9;
              v11 = *((unsigned __int8 *)Instance + 16);
              v58 = &v19;
              v14 = v11;
              v54 = &v21;
              v66 = v16;
              v50 = &v23;
              *(_DWORD *)&EventDescriptor.Level = 4;
              v46 = &v25;
              v44 = &v15;
              v42 = &v12;
              UserData.Ptr = (ULONGLONG)off_18009A350;
              v40 = &v14;
              v38 = &v26;
              v16[0] = 0x1000000;
              v17 = 16;
              v18 = (char *)Instance + 72;
              v19 = 16;
              v20 = (char *)Instance + 56;
              v21 = 16;
              v22 = (char *)Instance + 40;
              v23 = 16;
              v24 = (char *)Instance + 24;
              v25 = 16;
              v15 = 16;
              v26 = v10;
              v67 = 8;
              v62 = &v17;
              v63 = 2;
              v65 = 16;
              v59 = 2;
              v60 = (char *)Instance + 72;
              v61 = 16;
              v55 = 2;
              v56 = (char *)Instance + 56;
              v57 = 16;
              v51 = 2;
              v52 = (char *)Instance + 40;
              v53 = 16;
              v47 = 2;
              v48 = (char *)Instance + 24;
              v49 = 16;
              v45 = 8;
              v43 = 2;
              v41 = 4;
              v39 = 16;
              *(_DWORD *)&EventDescriptor.Id = 184549376;
              EventDescriptor.Keyword = 0x400000000000LL;
              UserData.Size = *(unsigned __int16 *)off_18009A350;
              v35 = byte_18008CDCB;
              UserData.Reserved = 2;
              v36 = 148;
              v37 = 1;
              v13 = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
              EventWriteTransfer(RegHandle, &EventDescriptor, 0, 0, 0x11u, &UserData);
            }
          }
          else if ( (unsigned int)dword_18009A348 > 4
                 && (qword_18009A358 & 0x400000000000LL) != 0
                 && (qword_18009A360 & 0x400000000000LL) == qword_18009A360 )
          {
            v15 = 0x1000000;
            v32 = &v15;
            *(_DWORD *)&EventDescriptor.Level = 4;
            v28.Ptr = (ULONGLONG)off_18009A350;
            v33 = 8;
            *(_DWORD *)&EventDescriptor.Id = 184549376;
            EventDescriptor.Keyword = 0x400000000000LL;
            v28.Size = *(unsigned __int16 *)off_18009A350;
            v29 = byte_18008CD95;
            v28.Reserved = 2;
            v30 = 42;
            v31 = 1;
            v13 = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
            EventWriteTransfer(RegHandle, &EventDescriptor, 0, 0, 3u, &v28);
          }
        }
        else if ( (v8 & 6) == 4 )
        {
          ProcessBootErrorLogLaunch(v4[10], 1);
        }
        goto LABEL_33;
      }
      v5 = (__int64 **)v4[2];
      if ( *((_BYTE *)v5 + 25) )
      {
        for ( i = (__int64 *)v4[1]; !*((_BYTE *)i + 25); i = (__int64 *)i[1] )
        {
          if ( v4 != (__int64 *)i[2] )
            break;
          v4 = i;
        }
        v4 = i;
      }
      else
      {
        v4 = (__int64 *)v4[2];
        for ( j = *v5; !*((_BYTE *)j + 25); j = (__int64 *)*j )
          v4 = j;
      }
    }
    goto LABEL_33;
  }
  v3 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
    return;
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 132, &WPP_87bbf11076dc3c61a5de4204d50ff79d_Traceguids);
LABEL_33:
    v3 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( v3 != &WPP_GLOBAL_Control && (*((_BYTE *)v3 + 28) & 0x20) != 0 )
    WPP_SF_(v3[2], 133, &WPP_87bbf11076dc3c61a5de4204d50ff79d_Traceguids);
}

```

## disassembly

```asm
0x180029830  push    rbp
0x180029832  push    rbx
0x180029833  push    rdi
0x180029834  push    r14
0x180029836  lea     rbp, [rsp-118h]
0x18002983e  sub     rsp, 218h
0x180029845  mov     rax, cs:__security_cookie
0x18002984c  xor     rax, rsp
0x18002984f  mov     [rbp+130h+var_30], rax
0x180029856  mov     rbx, rcx
0x180029859  mov     rcx, cs:WPP_GLOBAL_Control
0x180029860  lea     r14, WPP_GLOBAL_Control
0x180029867  cmp     rcx, r14
0x18002986a  jz      short loc_180029887
0x18002986c  test    byte ptr [rcx+1Ch], 20h
0x180029870  jz      short loc_180029887
0x180029872  mov     rcx, [rcx+10h]
0x180029876  lea     r8, WPP_87bbf11076dc3c61a5de4204d50ff79d_Traceguids
0x18002987d  mov     edx, 83h
0x180029882  call    WPP_SF_
0x180029887  call    ?getInstance@RecoveryTelemetery@@SAPEAV1@XZ; RecoveryTelemetery::getInstance(void)
0x18002988c  mov     rdi, rax
0x18002988f  test    rbx, rbx
0x180029892  jnz     short loc_1800298C8
0x180029894  mov     rcx, cs:WPP_GLOBAL_Control
0x18002989b  cmp     rcx, r14
0x18002989e  jz      loc_180029CD4
0x1800298a4  test    byte ptr [rcx+1Ch], 2
0x1800298a8  jz      loc_180029CB4
0x1800298ae  mov     rcx, [rcx+10h]
0x1800298b2  lea     r8, WPP_87bbf11076dc3c61a5de4204d50ff79d_Traceguids
0x1800298b9  mov     edx, 84h
0x1800298be  call    WPP_SF_
0x1800298c3  jmp     loc_180029CAD
0x1800298c8  mov     r8, [rbx]
0x1800298cb  mov     rcx, [r8]
0x1800298ce  xchg    ax, ax
0x1800298d0  cmp     rcx, r8
0x1800298d3  jz      loc_180029CAD
0x1800298d9  cmp     dword ptr [rcx+58h], 0
0x1800298dd  jz      short loc_1800298E8
0x1800298df  test    dword ptr [rcx+40h], 4000h
0x1800298e6  jnz     short loc_180029941
0x1800298e8  mov     rdx, [rcx+10h]
0x1800298ec  cmp     byte ptr [rdx+19h], 0
0x1800298f0  jz      short loc_180029918
0x1800298f2  mov     rax, [rcx+8]
0x1800298f6  cmp     byte ptr [rax+19h], 0
0x1800298fa  jnz     short loc_180029913
0x1800298fc  nop     dword ptr [rax+00h]
0x180029900  cmp     rcx, [rax+10h]
0x180029904  jnz     short loc_180029913
0x180029906  mov     rcx, rax
0x180029909  mov     rax, [rax+8]
0x18002990d  cmp     byte ptr [rax+19h], 0
0x180029911  jz      short loc_180029900
0x180029913  mov     rcx, rax
0x180029916  jmp     short loc_1800298D0
0x180029918  mov     rcx, rdx
0x18002991b  mov     rdx, [rdx]
0x18002991e  cmp     byte ptr [rdx+19h], 0
0x180029922  jnz     short loc_1800298D0
0x180029924  nop     dword ptr [rax+00h]
0x180029928  nop     dword ptr [rax+rax+00000000h]
0x180029930  mov     rax, [rdx]
0x180029933  mov     rcx, rdx
0x180029936  mov     rdx, rax
0x180029939  cmp     byte ptr [rax+19h], 0
0x18002993d  jz      short loc_180029930
0x18002993f  jmp     short loc_1800298D0
0x180029941  mov     eax, [rcx+40h]
0x180029944  test    al, 1
0x180029946  jz      loc_180029C99
0x18002994c  mov     rcx, [rcx+50h]; __int64
0x180029950  xor     edx, edx; int
0x180029952  call    ?ProcessBootErrorLogLaunch@@YAX_JH@Z; ProcessBootErrorLogLaunch(__int64,int)
0x180029957  test    rdi, rdi
0x18002995a  jz      loc_180029BB2
0x180029960  cmp     byte ptr [rdi+10h], 0
0x180029964  jz      loc_180029BB2
0x18002996a  mov     eax, cs:dword_18009A348
0x180029970  cmp     eax, 4
0x180029973  jbe     loc_180029CAD
0x180029979  mov     rcx, cs:qword_18009A360
0x180029980  mov     r11, 400000000000h
0x18002998a  mov     rax, cs:qword_18009A358
0x180029991  test    r11, rax
0x180029994  jz      loc_180029CAD
0x18002999a  mov     rax, rcx
0x18002999d  and     rax, r11
0x1800299a0  cmp     rax, rcx
0x1800299a3  jnz     loc_180029CAD
0x1800299a9  mov     [rsp+230h+arg_0], rsi
0x1800299b1  movzx   eax, word ptr [rdi+14h]
0x1800299b5  lea     rcx, [rdi+58h]
0x1800299b9  movups  xmm0, xmmword ptr [rdi]
0x1800299bc  mov     esi, 10h
0x1800299c1  mov     [rsp+230h+var_1E0], rcx
0x1800299c6  mov     [rbp+130h+var_50], rcx
0x1800299cd  lea     rdx, [rdi+48h]
0x1800299d1  mov     [rsp+230h+var_200], ax
0x1800299d6  lea     rcx, [rsp+230h+var_1C8]
0x1800299db  movzx   eax, byte ptr [rdi+10h]
0x1800299df  lea     r8, [rdi+38h]
0x1800299e3  mov     [rbp+130h+var_80], rcx
0x1800299ea  lea     r9, [rdi+28h]
0x1800299ee  mov     [rsp+230h+var_1F8], eax
0x1800299f2  lea     rcx, [rsp+230h+var_1B8]
0x1800299f7  mov     [rbp+130h+var_A0], rcx
0x1800299fe  lea     rax, [rsp+230h+var_1E8]
0x180029a03  mov     [rbp+130h+var_40], rax
0x180029a0a  lea     rcx, [rbp+130h+var_1A8]
0x180029a0e  movzx   eax, cs:word_18008CDC1
0x180029a15  lea     r10, [rdi+18h]
0x180029a19  mov     [rbp+130h+var_C0], rcx
0x180029a1d  lea     rbx, [rsp+230h+var_1D8]
0x180029a22  mov     dword ptr [rbp+130h+EventDescriptor.Level], eax
0x180029a25  lea     rcx, [rbp+130h+var_198]
0x180029a29  mov     rax, cs:off_18009A350
0x180029a30  mov     [rbp+130h+var_E0], rcx
0x180029a34  lea     rcx, [rsp+230h+var_1F0]
0x180029a39  mov     [rbp+130h+var_F0], rcx
0x180029a3d  lea     rcx, [rsp+230h+var_200]
0x180029a42  mov     [rbp+130h+var_100], rcx
0x180029a46  lea     rcx, [rsp+230h+var_1F8]
0x180029a4b  mov     [rbp+130h+var_140.Ptr], rax
0x180029a4f  mov     [rbp+130h+var_110], rcx
0x180029a53  lea     rcx, [rbp+130h+var_190]
0x180029a57  mov     [rbp+130h+var_120], rcx
0x180029a5b  lea     rcx, _TraceLoggingMetadata
0x180029a62  mov     [rsp+230h+var_1E8], 1000000h
0x180029a6b  mov     [rsp+230h+var_1D8], si
0x180029a70  mov     [rsp+230h+var_1D0], rdx
0x180029a75  mov     [rsp+230h+var_1C8], si
0x180029a7a  mov     [rsp+230h+var_1C0], r8
0x180029a7f  mov     [rsp+230h+var_1B8], si
0x180029a84  mov     [rbp+130h+var_1B0], r9
0x180029a88  mov     [rbp+130h+var_1A8], si
0x180029a8c  mov     [rbp+130h+var_1A0], r10
0x180029a90  mov     [rbp+130h+var_198], si
0x180029a94  mov     [rsp+230h+var_1F0], rsi
0x180029a99  movups  [rbp+130h+var_190], xmm0
0x180029a9d  mov     [rbp+130h+var_38], 8
0x180029aa8  mov     [rbp+130h+var_60], rbx
0x180029aaf  mov     [rbp+130h+var_58], 2
0x180029aba  mov     [rbp+130h+var_48], rsi
0x180029ac1  mov     [rbp+130h+var_78], 2
0x180029acc  mov     [rbp+130h+var_70], rdx
0x180029ad3  mov     [rbp+130h+var_68], rsi
0x180029ada  mov     [rbp+130h+var_98], 2
0x180029ae5  mov     [rbp+130h+var_90], r8
0x180029aec  mov     [rbp+130h+var_88], rsi
0x180029af3  mov     [rbp+130h+var_B8], 2
0x180029afb  mov     [rbp+130h+var_B0], r9
0x180029b02  mov     [rbp+130h+var_A8], rsi
0x180029b09  mov     [rbp+130h+var_D8], 2
0x180029b11  mov     [rbp+130h+var_D0], r10
0x180029b15  mov     [rbp+130h+var_C8], rsi
0x180029b19  mov     [rbp+130h+var_E8], 8
0x180029b21  mov     [rbp+130h+var_F8], 2
0x180029b29  mov     [rbp+130h+var_108], 4
0x180029b31  mov     [rbp+130h+var_118], rsi
0x180029b35  mov     dword ptr [rbp+130h+EventDescriptor.Id], 0B000000h
0x180029b3c  mov     [rbp+130h+EventDescriptor.Keyword], r11
0x180029b40  movzx   eax, word ptr [rax]
0x180029b43  mov     [rbp+130h+var_140.Size], eax
0x180029b46  lea     rax, byte_18008CDCB
0x180029b4d  mov     [rbp+130h+var_130], rax
0x180029b51  lea     rax, _TraceLoggingMetadataEnd
0x180029b58  sub     eax, ecx
0x180029b5a  mov     dword ptr [rbp+130h+var_140.0Ch], 2
0x180029b61  mov     [rbp+130h+var_128], 94h
0x180029b68  mov     [rbp+130h+var_124], 1
0x180029b6f  mov     [rsp+230h+var_1FC], eax
0x180029b73  mov     eax, [rsp+230h+var_1FC]
0x180029b77  lea     rdx, [rbp+130h+EventDescriptor]; EventDescriptor
0x180029b7b  mov     rcx, cs:RegHandle; RegHandle
0x180029b82  lea     rax, [rbp+130h+var_140]
0x180029b86  mov     [rsp+230h+UserData], rax; UserData
0x180029b8b  xor     r9d, r9d; RelatedActivityId
0x180029b8e  xor     r8d, r8d; ActivityId
0x180029b91  mov     [rsp+230h+UserDataCount], 11h; UserDataCount
0x180029b99  call    cs:__imp_EventWriteTransfer
0x180029ba0  nop     dword ptr [rax+rax+00h]
0x180029ba5  mov     rsi, [rsp+230h+arg_0]
0x180029bad  jmp     loc_180029CAD
0x180029bb2  mov     eax, cs:dword_18009A348
0x180029bb8  cmp     eax, 4
0x180029bbb  jbe     loc_180029CAD
0x180029bc1  mov     rcx, cs:qword_18009A360
0x180029bc8  mov     r11, 400000000000h
0x180029bd2  mov     rax, cs:qword_18009A358
0x180029bd9  test    r11, rax
0x180029bdc  jz      loc_180029CAD
0x180029be2  mov     rax, rcx
0x180029be5  and     rax, r11
0x180029be8  cmp     rax, rcx
0x180029beb  jnz     loc_180029CAD
0x180029bf1  lea     rax, [rsp+230h+var_1F0]
0x180029bf6  mov     [rsp+230h+var_1F0], 1000000h
0x180029bff  mov     [rbp+130h+var_150], rax
0x180029c03  lea     rcx, _TraceLoggingMetadata
0x180029c0a  movzx   eax, cs:word_18008CD8B
0x180029c11  lea     rdx, [rbp+130h+EventDescriptor]; EventDescriptor
0x180029c15  mov     dword ptr [rbp+130h+EventDescriptor.Level], eax
0x180029c18  xor     r9d, r9d; RelatedActivityId
0x180029c1b  mov     rax, cs:off_18009A350
0x180029c22  xor     r8d, r8d; ActivityId
0x180029c25  mov     [rbp+130h+var_170.Ptr], rax
0x180029c29  mov     [rbp+130h+var_148], 8
0x180029c31  mov     dword ptr [rbp+130h+EventDescriptor.Id], 0B000000h
0x180029c38  mov     [rbp+130h+EventDescriptor.Keyword], r11
0x180029c3c  movzx   eax, word ptr [rax]
0x180029c3f  mov     [rbp+130h+var_170.Size], eax
0x180029c42  lea     rax, byte_18008CD95
0x180029c49  mov     [rbp+130h+var_160], rax
0x180029c4d  lea     rax, _TraceLoggingMetadataEnd
0x180029c54  sub     eax, ecx
0x180029c56  mov     dword ptr [rbp+130h+var_170.0Ch], 2
0x180029c5d  mov     [rbp+130h+var_158], 2Ah ; '*'
0x180029c64  mov     [rbp+130h+var_154], 1
0x180029c6b  mov     [rsp+230h+var_1FC], eax
0x180029c6f  mov     eax, [rsp+230h+var_1FC]
0x180029c73  mov     rcx, cs:RegHandle; RegHandle
0x180029c7a  lea     rax, [rbp+130h+var_170]
0x180029c7e  mov     [rsp+230h+UserData], rax; UserData
0x180029c83  mov     [rsp+230h+UserDataCount], 3; UserDataCount
0x180029c8b  call    cs:__imp_EventWriteTransfer
0x180029c92  nop     dword ptr [rax+rax+00h]
0x180029c97  jmp     short loc_180029CAD
0x180029c99  and     al, 6
0x180029c9b  cmp     al, 4
0x180029c9d  jnz     short loc_180029CAD
0x180029c9f  mov     rcx, [rcx+50h]; __int64
0x180029ca3  mov     edx, 1; int
0x180029ca8  call    ?ProcessBootErrorLogLaunch@@YAX_JH@Z; ProcessBootErrorLogLaunch(__int64,int)
0x180029cad  mov     rcx, cs:WPP_GLOBAL_Control
0x180029cb4  cmp     rcx, r14
0x180029cb7  jz      short loc_180029CD4
0x180029cb9  test    byte ptr [rcx+1Ch], 20h
0x180029cbd  jz      short loc_180029CD4
0x180029cbf  mov     rcx, [rcx+10h]
0x180029cc3  lea     r8, WPP_87bbf11076dc3c61a5de4204d50ff79d_Traceguids
0x180029cca  mov     edx, 85h
0x180029ccf  call    WPP_SF_
0x180029cd4  mov     rcx, [rbp+130h+var_30]
0x180029cdb  xor     rcx, rsp; StackCookie
0x180029cde  call    __security_check_cookie
0x180029ce3  add     rsp, 218h
0x180029cea  pop     r14
0x180029cec  pop     rdi
0x180029ced  pop     rbx
0x180029cee  pop     rbp
0x180029cef  retn
```
