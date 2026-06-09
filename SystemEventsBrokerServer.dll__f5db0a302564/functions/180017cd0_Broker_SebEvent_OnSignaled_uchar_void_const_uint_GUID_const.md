# Broker::SebEvent::OnSignaled(uchar,void const *,uint,_GUID const *)

- ea: `0x180017cd0`
- end: `0x180017f38`
- name: `?OnSignaled@SebEvent@Broker@@QEAAKEPEBXIPEBU_GUID@@@Z`
- size: `616`
- prototype: `unsigned int __fastcall(Broker::SebEvent *__hidden this, unsigned __int8, const void *, unsigned int, const struct _GUID *)`
- caller_count: `2`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180008630`
- `0x180017f40`

## callees

- `0x180001730`
- `0x180017cd0`
- `0x18001cf50`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180017f16`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180017f16`

## pseudocode

```c
__int64 __fastcall Broker::SebEvent::OnSignaled(
        Broker::SebEvent *this,
        char a2,
        const unsigned __int8 *a3,
        unsigned int a4)
{
  __int64 v4; // rsi
  unsigned __int64 v6; // rcx
  unsigned int v8; // ebx
  int v9; // eax
  unsigned __int8 *v10; // rdx
  __int64 result; // rax
  int v12; // ecx
  unsigned __int8 v13; // [rsp+30h] [rbp-D0h] BYREF
  int v14; // [rsp+34h] [rbp-CCh] BYREF
  unsigned int v15; // [rsp+38h] [rbp-C8h] BYREF
  int v16; // [rsp+3Ch] [rbp-C4h] BYREF
  int v17; // [rsp+40h] [rbp-C0h] BYREF
  int v18; // [rsp+44h] [rbp-BCh] BYREF
  int v19; // [rsp+48h] [rbp-B8h] BYREF
  int v20; // [rsp+4Ch] [rbp-B4h] BYREF
  _DWORD v21[2]; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v22; // [rsp+58h] [rbp-A8h] BYREF
  EVENT_DESCRIPTOR EventDescriptor; // [rsp+60h] [rbp-A0h] BYREF
  struct _EVENT_DATA_DESCRIPTOR UserData; // [rsp+70h] [rbp-90h] BYREF
  char *v25; // [rsp+80h] [rbp-80h]
  int v26; // [rsp+88h] [rbp-78h]
  int v27; // [rsp+8Ch] [rbp-74h]
  __int64 *v28; // [rsp+90h] [rbp-70h]
  __int64 v29; // [rsp+98h] [rbp-68h]
  __int64 v30; // [rsp+A0h] [rbp-60h]
  __int64 v31; // [rsp+A8h] [rbp-58h]
  _DWORD *v32; // [rsp+B0h] [rbp-50h]
  __int64 v33; // [rsp+B8h] [rbp-48h]
  int *v34; // [rsp+C0h] [rbp-40h]
  __int64 v35; // [rsp+C8h] [rbp-38h]
  int *v36; // [rsp+D0h] [rbp-30h]
  __int64 v37; // [rsp+D8h] [rbp-28h]
  int *v38; // [rsp+E0h] [rbp-20h]
  __int64 v39; // [rsp+E8h] [rbp-18h]
  int *v40; // [rsp+F0h] [rbp-10h]
  __int64 v41; // [rsp+F8h] [rbp-8h]
  int *v42; // [rsp+100h] [rbp+0h]
  __int64 v43; // [rsp+108h] [rbp+8h]
  unsigned int *v44; // [rsp+110h] [rbp+10h]
  __int64 v45; // [rsp+118h] [rbp+18h]
  int *v46; // [rsp+120h] [rbp+20h]
  __int64 v47; // [rsp+128h] [rbp+28h]

  v4 = a4;
  v13 = 0;
  v6 = *((unsigned int *)this + 46);
  v14 = 0;
  if ( v4 + 8 < v6 )
  {
    v8 = 87;
    v9 = 4096;
LABEL_12:
    if ( (unsigned int)dword_180035050 > 2 )
    {
      v12 = *((_DWORD *)this + 46);
      v14 = v9;
      v18 = *((_DWORD *)this + 43);
      v19 = *((_DWORD *)this + 34);
      v20 = *((_DWORD *)this + 33);
      v21[0] = *((_DWORD *)this + 50);
      v22 = *(_QWORD *)((char *)this + 124);
      v46 = &v14;
      v44 = &v15;
      v42 = &v16;
      v40 = &v17;
      v38 = &v18;
      v36 = &v19;
      v34 = &v20;
      v32 = v21;
      v30 = *((_QWORD *)this + 28);
      v28 = &v22;
      *(_DWORD *)&EventDescriptor.Level = 2;
      UserData.Ptr = (ULONGLONG)off_180035058;
      v16 = v12;
      v15 = v8;
      v17 = v4;
      v47 = 4;
      v45 = 4;
      v43 = 4;
      v41 = 4;
      v39 = 4;
      v37 = 4;
      v35 = 4;
      v33 = 4;
      v31 = 16;
      v29 = 8;
      *(_DWORD *)&EventDescriptor.Id = 184549376;
      EventDescriptor.Keyword = 0;
      UserData.Size = *(unsigned __int16 *)off_180035058;
      v25 = &byte_18002DEAF;
      UserData.Reserved = 2;
      v26 = 139;
      v27 = 1;
      v21[1] = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
      EventWriteTransfer(RegHandle, &EventDescriptor, 0, 0, 0xCu, &UserData);
    }
    return v8;
  }
  if ( (unsigned int)v6 > 8 && !a3 )
  {
    v8 = 87;
    v9 = 0x2000;
    goto LABEL_12;
  }
  if ( (unsigned int)(v4 - 1) <= 0x12 )
  {
    v8 = 87;
    v9 = 12288;
    goto LABEL_12;
  }
  v10 = 0;
  if ( *((_DWORD *)this + 25) )
  {
    v10 = &v13;
    v13 = a2 != 0;
  }
  result = Broker::SebEvent::SignalSyncEvent(this, v10, a3, v4, 0, (enum _BI_ACTIVATION_STATUS *)&v14);
  v8 = result;
  if ( (_DWORD)result )
  {
    v9 = 0x4000;
    goto LABEL_12;
  }
  return result;
}

```

## disassembly

```asm
0x180017cd0  push    rbp
0x180017cd2  push    rbx
0x180017cd3  push    rsi
0x180017cd4  push    rdi
0x180017cd5  push    r14
0x180017cd7  lea     rbp, [rsp-40h]
0x180017cdc  sub     rsp, 140h
0x180017ce3  mov     rax, cs:__security_cookie
0x180017cea  xor     rax, rsp
0x180017ced  mov     [rbp+60h+var_30], rax
0x180017cf1  mov     esi, r9d
0x180017cf4  xor     r14d, r14d
0x180017cf7  mov     rdi, rcx
0x180017cfa  mov     [rsp+160h+var_130], 0
0x180017cff  mov     ecx, [rcx+0B8h]
0x180017d05  movzx   r9d, dl
0x180017d09  mov     [rsp+160h+var_12C], r14d
0x180017d0e  lea     rax, [rsi+8]
0x180017d12  cmp     rax, rcx
0x180017d15  jnb     short loc_180017D23
0x180017d17  mov     ebx, 57h ; 'W'
0x180017d1c  mov     eax, 1000h
0x180017d21  jmp     short loc_180017D8C
0x180017d23  cmp     ecx, 8
0x180017d26  jbe     short loc_180017D39
0x180017d28  test    r8, r8
0x180017d2b  jnz     short loc_180017D39
0x180017d2d  mov     ebx, 57h ; 'W'
0x180017d32  mov     eax, 2000h
0x180017d37  jmp     short loc_180017D8C
0x180017d39  lea     eax, [rsi-1]
0x180017d3c  cmp     eax, 12h
0x180017d3f  ja      short loc_180017D4D
0x180017d41  mov     ebx, 57h ; 'W'
0x180017d46  mov     eax, 3000h
0x180017d4b  jmp     short loc_180017D8C
0x180017d4d  mov     rdx, r14
0x180017d50  cmp     [rdi+64h], r14d
0x180017d54  jz      short loc_180017D63
0x180017d56  test    r9b, r9b
0x180017d59  lea     rdx, [rsp+160h+var_130]; unsigned __int8 *
0x180017d5e  setnz   [rsp+160h+var_130]
0x180017d63  lea     rax, [rsp+160h+var_12C]
0x180017d68  mov     r9d, esi; unsigned int
0x180017d6b  mov     [rsp+160h+UserData], rax; enum _BI_ACTIVATION_STATUS *
0x180017d70  mov     rcx, rdi; this
0x180017d73  mov     qword ptr [rsp+160h+UserDataCount], r14; struct _GUID *
0x180017d78  call    ?SignalSyncEvent@SebEvent@Broker@@QEAAKPEAEPEBEKPEBU_GUID@@PEAW4_BI_ACTIVATION_STATUS@@@Z; Broker::SebEvent::SignalSyncEvent(uchar *,uchar const *,ulong,_GUID const *,_BI_ACTIVATION_STATUS *)
0x180017d7d  mov     ebx, eax
0x180017d7f  test    eax, eax
0x180017d81  jz      loc_180017F1E
0x180017d87  mov     eax, 4000h
0x180017d8c  mov     ecx, cs:dword_180035050
0x180017d92  cmp     ecx, 2
0x180017d95  jbe     loc_180017F1C
0x180017d9b  mov     ecx, [rdi+0B8h]
0x180017da1  lea     rdx, [rsp+160h+EventDescriptor]; EventDescriptor
0x180017da6  mov     [rsp+160h+var_12C], eax
0x180017daa  xor     r9d, r9d; RelatedActivityId
0x180017dad  mov     eax, [rdi+0ACh]
0x180017db3  xor     r8d, r8d; ActivityId
0x180017db6  mov     [rsp+160h+var_11C], eax
0x180017dba  mov     eax, [rdi+88h]
0x180017dc0  mov     [rsp+160h+var_118], eax
0x180017dc4  mov     eax, [rdi+84h]
0x180017dca  mov     [rsp+160h+var_114], eax
0x180017dce  mov     eax, [rdi+0C8h]
0x180017dd4  mov     [rsp+160h+var_110], eax
0x180017dd8  mov     rax, [rdi+7Ch]
0x180017ddc  mov     [rsp+160h+var_108], rax
0x180017de1  lea     rax, [rsp+160h+var_12C]
0x180017de6  mov     [rbp+60h+var_40], rax
0x180017dea  lea     rax, [rsp+160h+var_128]
0x180017def  mov     [rbp+60h+var_50], rax
0x180017df3  lea     rax, [rsp+160h+var_124]
0x180017df8  mov     [rbp+60h+var_60], rax
0x180017dfc  lea     rax, [rsp+160h+var_120]
0x180017e01  mov     [rbp+60h+var_70], rax
0x180017e05  lea     rax, [rsp+160h+var_11C]
0x180017e0a  mov     [rbp+60h+var_80], rax
0x180017e0e  lea     rax, [rsp+160h+var_118]
0x180017e13  mov     [rbp+60h+var_90], rax
0x180017e17  lea     rax, [rsp+160h+var_114]
0x180017e1c  mov     [rbp+60h+var_A0], rax
0x180017e20  lea     rax, [rsp+160h+var_110]
0x180017e25  mov     [rbp+60h+var_B0], rax
0x180017e29  mov     rax, [rdi+0E0h]
0x180017e30  mov     [rbp+60h+var_C0], rax
0x180017e34  lea     rax, [rsp+160h+var_108]
0x180017e39  mov     [rbp+60h+var_D0], rax
0x180017e3d  movzx   eax, cs:word_18002DEA5
0x180017e44  mov     dword ptr [rsp+160h+EventDescriptor.Level], eax
0x180017e48  mov     rax, cs:off_180035058
0x180017e4f  mov     [rsp+160h+var_F0.Ptr], rax
0x180017e54  mov     [rsp+160h+var_124], ecx
0x180017e58  lea     rcx, _TraceLoggingMetadata
0x180017e5f  mov     [rsp+160h+var_128], ebx
0x180017e63  mov     [rsp+160h+var_120], esi
0x180017e67  mov     [rbp+60h+var_38], 4
0x180017e6f  mov     [rbp+60h+var_48], 4
0x180017e77  mov     [rbp+60h+var_58], 4
0x180017e7f  mov     [rbp+60h+var_68], 4
0x180017e87  mov     [rbp+60h+var_78], 4
0x180017e8f  mov     [rbp+60h+var_88], 4
0x180017e97  mov     [rbp+60h+var_98], 4
0x180017e9f  mov     [rbp+60h+var_A8], 4
0x180017ea7  mov     [rbp+60h+var_B8], 10h
0x180017eaf  mov     [rbp+60h+var_C8], 8
0x180017eb7  mov     dword ptr [rsp+160h+EventDescriptor.Id], 0B000000h
0x180017ebf  mov     [rsp+160h+EventDescriptor.Keyword], r14
0x180017ec4  movzx   eax, word ptr [rax]
0x180017ec7  mov     [rsp+160h+var_F0.Size], eax
0x180017ecb  lea     rax, byte_18002DEAF
0x180017ed2  mov     [rbp+60h+var_E0], rax
0x180017ed6  lea     rax, _TraceLoggingMetadataEnd
0x180017edd  sub     eax, ecx
0x180017edf  mov     dword ptr [rsp+160h+var_F0.0Ch], 2
0x180017ee7  mov     [rbp+60h+var_D8], 8Bh
0x180017eee  mov     [rbp+60h+var_D4], 1
0x180017ef5  mov     [rsp+160h+var_10C], eax
0x180017ef9  mov     eax, [rsp+160h+var_10C]
0x180017efd  mov     rcx, cs:RegHandle; RegHandle
0x180017f04  lea     rax, [rsp+160h+var_F0]
0x180017f09  mov     [rsp+160h+UserData], rax; UserData
0x180017f0e  mov     [rsp+160h+UserDataCount], 0Ch; UserDataCount
0x180017f16  call    cs:__imp_EventWriteTransfer
0x180017f1c  mov     eax, ebx
0x180017f1e  mov     rcx, [rbp+60h+var_30]
0x180017f22  xor     rcx, rsp; StackCookie
0x180017f25  call    __security_check_cookie
0x180017f2a  add     rsp, 140h
0x180017f31  pop     r14
0x180017f33  pop     rdi
0x180017f34  pop     rsi
0x180017f35  pop     rbx
0x180017f36  pop     rbp
0x180017f37  retn
```
