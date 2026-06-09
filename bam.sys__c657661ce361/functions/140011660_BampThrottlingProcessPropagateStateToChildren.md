# BampThrottlingProcessPropagateStateToChildren

- ea: `0x140011660`
- end: `0x14001191d`
- name: `BampThrottlingProcessPropagateStateToChildren`
- size: `701`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x140011560`

## callees

- `0x1400026d0`
- `0x140010990`
- `0x140011160`
- `0x140011660`

## import_xrefs

- `ntoskrnl!EtwWriteTransfer` at `0x140011848`
- `ntoskrnl!EtwWriteTransfer` at `0x140011848`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140011875`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140011875`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x14001188a`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x14001188a`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400118d8`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400118d8`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x1400118cc`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x1400118cc`

## pseudocode

```c
bool __fastcall BampThrottlingProcessPropagateStateToChildren(__int64 a1, int **a2)
{
  __int64 v4; // rax
  int v5; // ecx
  int *v6; // rcx
  int *v7; // rax
  int v9; // [rsp+30h] [rbp-D0h] BYREF
  int v10; // [rsp+34h] [rbp-CCh] BYREF
  int v11; // [rsp+38h] [rbp-C8h] BYREF
  int v12; // [rsp+3Ch] [rbp-C4h] BYREF
  int v13; // [rsp+40h] [rbp-C0h] BYREF
  int v14; // [rsp+44h] [rbp-BCh] BYREF
  int v15; // [rsp+48h] [rbp-B8h] BYREF
  int v16; // [rsp+4Ch] [rbp-B4h] BYREF
  int v17; // [rsp+50h] [rbp-B0h] BYREF
  int v18; // [rsp+54h] [rbp-ACh] BYREF
  _DWORD v19[2]; // [rsp+58h] [rbp-A8h] BYREF
  EVENT_DESCRIPTOR EventDescriptor; // [rsp+60h] [rbp-A0h] BYREF
  struct _EVENT_DATA_DESCRIPTOR UserData; // [rsp+70h] [rbp-90h] BYREF
  char *v22; // [rsp+80h] [rbp-80h]
  int v23; // [rsp+88h] [rbp-78h]
  int v24; // [rsp+8Ch] [rbp-74h]
  int *v25; // [rsp+90h] [rbp-70h]
  __int64 v26; // [rsp+98h] [rbp-68h]
  int *v27; // [rsp+A0h] [rbp-60h]
  __int64 v28; // [rsp+A8h] [rbp-58h]
  int *v29; // [rsp+B0h] [rbp-50h]
  __int64 v30; // [rsp+B8h] [rbp-48h]
  int *v31; // [rsp+C0h] [rbp-40h]
  __int64 v32; // [rsp+C8h] [rbp-38h]
  int *v33; // [rsp+D0h] [rbp-30h]
  __int64 v34; // [rsp+D8h] [rbp-28h]
  int *v35; // [rsp+E0h] [rbp-20h]
  __int64 v36; // [rsp+E8h] [rbp-18h]
  int *v37; // [rsp+F0h] [rbp-10h]
  __int64 v38; // [rsp+F8h] [rbp-8h]
  int *v39; // [rsp+100h] [rbp+0h]
  __int64 v40; // [rsp+108h] [rbp+8h]
  int *v41; // [rsp+110h] [rbp+10h]
  __int64 v42; // [rsp+118h] [rbp+18h]
  int *v43; // [rsp+120h] [rbp+20h]
  __int64 v44; // [rsp+128h] [rbp+28h]
  _DWORD *v45; // [rsp+130h] [rbp+30h]
  __int64 v46; // [rsp+138h] [rbp+38h]

  if ( (unsigned int)dword_140007010 > 4 )
  {
    v4 = *(_QWORD *)(a1 + 8);
    *(_DWORD *)&EventDescriptor.Id = 184549376;
    EventDescriptor.Keyword = 0;
    v5 = *(_DWORD *)(v4 + 464);
    v25 = &v9;
    v9 = v5;
    v6 = *a2;
    v26 = 4;
    v10 = *v6;
    v27 = &v10;
    v28 = 4;
    v11 = v6[1];
    v29 = &v11;
    v30 = 4;
    v12 = v6[3];
    v31 = &v12;
    v32 = 4;
    v13 = v6[4];
    v33 = &v13;
    v34 = 4;
    v14 = v6[5];
    v35 = &v14;
    v15 = *(_DWORD *)(a1 + 328);
    v37 = &v15;
    v16 = *(_DWORD *)(a1 + 332);
    v39 = &v16;
    v17 = *(_DWORD *)(a1 + 340);
    v41 = &v17;
    v18 = *(_DWORD *)(a1 + 344);
    v43 = &v18;
    v19[0] = *(_DWORD *)(a1 + 348);
    v45 = v19;
    *(_DWORD *)&EventDescriptor.Level = 4;
    UserData.Ptr = (ULONGLONG)off_140007018;
    v36 = 4;
    v38 = 4;
    v40 = 4;
    v42 = 4;
    v44 = 4;
    v46 = 4;
    UserData.Size = *(unsigned __int16 *)off_140007018;
    v22 = &byte_140005327;
    UserData.Reserved = 2;
    v23 = 216;
    v24 = 1;
    v19[1] = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
    EtwWriteTransfer(RegHandle, &EventDescriptor, 0, 0, 0xDu, &UserData);
  }
  v7 = *a2;
  *(_OWORD *)(a1 + 328) = *(_OWORD *)*a2;
  *(_QWORD *)(a1 + 344) = *((_QWORD *)v7 + 2);
  if ( ((_DWORD)a2[1] & 1) != 0 )
  {
    KeEnterCriticalRegion();
    ExAcquirePushLockExclusiveEx(&qword_140007588, 0);
    qword_140007590 = (__int64)KeGetCurrentThread();
    BampQueueThrottledProcessActionItem(a1, 1, 0, 2);
    qword_140007590 = 0;
    ExReleasePushLockExclusiveEx(&qword_140007588, 0);
    KeLeaveCriticalRegion();
  }
  else
  {
    BampQueuePolicyActionItemAfterStateChange(a1);
  }
  return (*(_DWORD *)(a1 + 304) & 1) == 0;
}

```

## disassembly

```asm
0x140011660  mov     [rsp-8+arg_8], rbx
0x140011665  mov     [rsp-8+arg_10], rsi
0x14001166a  push    rbp
0x14001166b  push    rdi
0x14001166c  push    r14
0x14001166e  lea     rbp, [rsp-50h]
0x140011673  sub     rsp, 150h
0x14001167a  mov     rax, cs:__security_cookie
0x140011681  xor     rax, rsp
0x140011684  mov     [rbp+60h+var_20], rax
0x140011688  mov     eax, cs:dword_140007010
0x14001168e  xor     r14d, r14d
0x140011691  mov     rsi, rdx
0x140011694  mov     rbx, rcx
0x140011697  cmp     eax, 4
0x14001169a  jbe     loc_140011854
0x1400116a0  mov     rax, [rcx+8]
0x1400116a4  xor     r9d, r9d; RelatedActivityId
0x1400116a7  mov     dword ptr [rsp+160h+EventDescriptor.Id], 0B000000h
0x1400116af  mov     [rsp+160h+EventDescriptor.Keyword], r14
0x1400116b4  mov     ecx, [rax+1D0h]
0x1400116ba  lea     rax, [rsp+160h+var_130]
0x1400116bf  mov     [rbp+60h+var_D0], rax
0x1400116c3  mov     [rsp+160h+var_130], ecx
0x1400116c7  mov     rcx, [rdx]
0x1400116ca  lea     rdx, [rsp+160h+EventDescriptor]; EventDescriptor
0x1400116cf  mov     [rbp+60h+var_C8], 4
0x1400116d7  mov     eax, [rcx]
0x1400116d9  mov     [rsp+160h+var_12C], eax
0x1400116dd  lea     rax, [rsp+160h+var_12C]
0x1400116e2  mov     [rbp+60h+var_C0], rax
0x1400116e6  mov     [rbp+60h+var_B8], 4
0x1400116ee  mov     eax, [rcx+4]
0x1400116f1  mov     [rsp+160h+var_128], eax
0x1400116f5  lea     rax, [rsp+160h+var_128]
0x1400116fa  mov     [rbp+60h+var_B0], rax
0x1400116fe  mov     [rbp+60h+var_A8], 4
0x140011706  mov     eax, [rcx+0Ch]
0x140011709  mov     [rsp+160h+var_124], eax
0x14001170d  lea     rax, [rsp+160h+var_124]
0x140011712  mov     [rbp+60h+var_A0], rax
0x140011716  mov     [rbp+60h+var_98], 4
0x14001171e  mov     eax, [rcx+10h]
0x140011721  mov     [rsp+160h+var_120], eax
0x140011725  lea     rax, [rsp+160h+var_120]
0x14001172a  mov     [rbp+60h+var_90], rax
0x14001172e  mov     [rbp+60h+var_88], 4
0x140011736  mov     eax, [rcx+14h]
0x140011739  lea     rcx, _TraceLoggingMetadata
0x140011740  mov     [rsp+160h+var_11C], eax
0x140011744  lea     rax, [rsp+160h+var_11C]
0x140011749  mov     [rbp+60h+var_80], rax
0x14001174d  mov     eax, [rbx+148h]
0x140011753  mov     [rsp+160h+var_118], eax
0x140011757  lea     rax, [rsp+160h+var_118]
0x14001175c  mov     [rbp+60h+var_70], rax
0x140011760  mov     eax, [rbx+14Ch]
0x140011766  mov     [rsp+160h+var_114], eax
0x14001176a  lea     rax, [rsp+160h+var_114]
0x14001176f  mov     [rbp+60h+var_60], rax
0x140011773  mov     eax, [rbx+154h]
0x140011779  mov     [rsp+160h+var_110], eax
0x14001177d  lea     rax, [rsp+160h+var_110]
0x140011782  mov     [rbp+60h+var_50], rax
0x140011786  mov     eax, [rbx+158h]
0x14001178c  mov     [rsp+160h+var_10C], eax
0x140011790  lea     rax, [rsp+160h+var_10C]
0x140011795  mov     [rbp+60h+var_40], rax
0x140011799  mov     eax, [rbx+15Ch]
0x14001179f  mov     [rsp+160h+var_108], eax
0x1400117a3  lea     rax, [rsp+160h+var_108]
0x1400117a8  mov     [rbp+60h+var_30], rax
0x1400117ac  movzx   eax, cs:word_14000531D
0x1400117b3  mov     dword ptr [rsp+160h+EventDescriptor.Level], eax
0x1400117b7  mov     rax, cs:off_140007018
0x1400117be  mov     [rsp+160h+var_F0.Ptr], rax
0x1400117c3  mov     [rbp+60h+var_78], 4
0x1400117cb  mov     [rbp+60h+var_68], 4
0x1400117d3  mov     [rbp+60h+var_58], 4
0x1400117db  mov     [rbp+60h+var_48], 4
0x1400117e3  mov     [rbp+60h+var_38], 4
0x1400117eb  mov     [rbp+60h+var_28], 4
0x1400117f3  movzx   eax, word ptr [rax]
0x1400117f6  mov     [rsp+160h+var_F0.Size], eax
0x1400117fa  lea     rax, byte_140005327
0x140011801  mov     [rbp+60h+var_E0], rax
0x140011805  lea     rax, _TraceLoggingMetadataEnd
0x14001180c  sub     eax, ecx
0x14001180e  mov     dword ptr [rsp+160h+var_F0.0Ch], 2
0x140011816  mov     [rbp+60h+var_D8], 0D8h
0x14001181d  xor     r8d, r8d; ActivityId
0x140011820  mov     [rbp+60h+var_D4], 1
0x140011827  mov     [rsp+160h+var_104], eax
0x14001182b  mov     eax, [rsp+160h+var_104]
0x14001182f  lea     rax, [rsp+160h+var_F0]
0x140011834  mov     [rsp+160h+UserData], rax; UserData
0x140011839  mov     [rsp+160h+UserDataCount], 0Dh; UserDataCount
0x140011841  mov     rcx, cs:RegHandle; RegHandle
0x140011848  call    cs:__imp_EtwWriteTransfer
0x14001184f  nop     dword ptr [rax+rax+00h]
0x140011854  mov     rax, [rsi]
0x140011857  movups  xmm0, xmmword ptr [rax]
0x14001185a  movups  xmmword ptr [rbx+148h], xmm0
0x140011861  movsd   xmm1, qword ptr [rax+10h]
0x140011866  movsd   qword ptr [rbx+158h], xmm1
0x14001186e  mov     eax, [rsi+8]
0x140011871  test    al, 1
0x140011873  jz      short loc_1400118E6
0x140011875  call    cs:__imp_KeEnterCriticalRegion
0x14001187c  nop     dword ptr [rax+rax+00h]
0x140011881  xor     edx, edx
0x140011883  lea     rcx, qword_140007588
0x14001188a  call    cs:__imp_ExAcquirePushLockExclusiveEx
0x140011891  nop     dword ptr [rax+rax+00h]
0x140011896  mov     rax, gs:188h
0x14001189f  mov     r9d, 2
0x1400118a5  xor     r8d, r8d
0x1400118a8  mov     cs:qword_140007590, rax
0x1400118af  mov     edx, 1
0x1400118b4  mov     rcx, rbx
0x1400118b7  call    BampQueueThrottledProcessActionItem
0x1400118bc  xor     edx, edx
0x1400118be  mov     cs:qword_140007590, r14
0x1400118c5  lea     rcx, qword_140007588
0x1400118cc  call    cs:__imp_ExReleasePushLockExclusiveEx
0x1400118d3  nop     dword ptr [rax+rax+00h]
0x1400118d8  call    cs:__imp_KeLeaveCriticalRegion
0x1400118df  nop     dword ptr [rax+rax+00h]
0x1400118e4  jmp     short loc_1400118EE
0x1400118e6  mov     rcx, rbx
0x1400118e9  call    BampQueuePolicyActionItemAfterStateChange
0x1400118ee  mov     eax, [rbx+130h]
0x1400118f4  not     al
0x1400118f6  and     al, 1
0x1400118f8  mov     rcx, [rbp+60h+var_20]
0x1400118fc  xor     rcx, rsp; StackCookie
0x1400118ff  call    __security_check_cookie
0x140011904  lea     r11, [rsp+160h+var_10]
0x14001190c  mov     rbx, [r11+28h]
0x140011910  mov     rsi, [r11+30h]
0x140011914  mov     rsp, r11
0x140011917  pop     r14
0x140011919  pop     rdi
0x14001191a  pop     rbp
0x14001191b  retn
```
