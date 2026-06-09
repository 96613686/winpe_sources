# WindowsInternal::ApplicationModel::Calls::IncomingCallToastStatics::_ShouldButtonBeVisible(PH_CALL_INFO const &,uint,int,WindowsInternal::ApplicationModel::Calls::IncomingToastAction)

- ea: `0x180015020`
- end: `0x18001528f`
- name: `?_ShouldButtonBeVisible@IncomingCallToastStatics@Calls@ApplicationModel@WindowsInternal@@MEAA_NAEBUPH_CALL_INFO@@IHW4IncomingToastAction@234@@Z`
- size: `623`
- prototype: ``
- caller_count: `0`
- callee_count: `9`
- tags: `broker_com_uri`

## callees

- `0x1800011fc`
- `0x180001dc0`
- `0x1800027c0`
- `0x180004b4c`
- `0x180011e5c`
- `0x180011e68`
- `0x1800127d8`
- `0x180015020`
- `0x1800165c4`

## import_xrefs

- `api-ms-win-core-heap-obsolete-l1-1-0!LocalFree` at `0x18001523d`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalFree` at `0x18001523d`
- `PhoneOm!PhoneGetLinePublicInfo` at `0x1800151bd`
- `PhoneOm!PhoneGetLinePublicInfo` at `0x1800151bd`
- `PhoneUtil!RemoveMetadataFromNumber` at `0x180015218`
- `PhoneUtil!RemoveMetadataFromNumber` at `0x180015218`
- `PhoneUtil!IsNumberDialable` at `0x18001527e`
- `PhoneUtil!IsNumberDialable` at `0x18001527e`

## pseudocode

```c
bool __fastcall WindowsInternal::ApplicationModel::Calls::IncomingCallToastStatics::_ShouldButtonBeVisible(
        WindowsInternal::ApplicationModel::Calls::IncomingCallToastStatics *a1,
        __int64 a2,
        int a3,
        int a4,
        int a5)
{
  int v5; // r14d
  _OWORD *v6; // rsi
  char v7; // bl
  __int64 v10; // rdi
  __int64 v11; // rcx
  __int64 v12; // rcx
  bool v13; // zf
  int LinePublicInfo; // eax
  __int64 v15; // r8
  __int64 v16; // rdi
  __int64 v17; // rax
  int v18; // eax
  __int64 v19; // r8
  int v20; // ebx
  HLOCAL hMem[2]; // [rsp+30h] [rbp-D0h] BYREF
  _BYTE v23[552]; // [rsp+40h] [rbp-C0h] BYREF
  int v24; // [rsp+268h] [rbp+168h]
  struct _EVENT_DATA_DESCRIPTOR v25; // [rsp+270h] [rbp+170h] BYREF
  HLOCAL *v26; // [rsp+290h] [rbp+190h]
  __int64 v27; // [rsp+298h] [rbp+198h]

  v5 = *(_DWORD *)(a2 + 3244);
  v6 = (_OWORD *)(a2 + 3060);
  v7 = 0;
  v10 = a2;
  LOBYTE(a2) = *(_DWORD *)(a2 + 3040) == 4
            && (*(_OWORD *)hMem = *v6,
                !WindowsInternal::ApplicationModel::Calls::IncomingCallToastStatics::_AudioEndpointsAvailable(
                   a1,
                   (struct _GUID *)hMem));
  switch ( a5 )
  {
    case 0:
      memset_0(v23, 0, 0x230u);
      LinePublicInfo = PhoneGetLinePublicInfo(v6, v23);
      if ( LinePublicInfo < 0 )
      {
        Log_HREvent_1((unsigned int)LinePublicInfo, 0, v15, 655);
        return 0;
      }
      if ( *(_DWORD *)(v10 + 3040) != 4 )
        return 0;
      if ( (v24 & 0x800) == 0 )
        return 0;
      if ( *(_DWORD *)(v10 + 3036) != 2 )
        return 0;
      v16 = v10 + 160;
      if ( !v16 )
        return 0;
      hMem[0] = 0;
      v17 = tlx::replace<unsigned short *,void * (*)(void *),&void * LocalFree(void *),0>(hMem);
      v18 = RemoveMetadataFromNumber(v16, v17);
      if ( v18 >= 0 )
      {
        if ( (unsigned int)IsNumberDialable(hMem[0]) )
        {
          v20 = 1;
LABEL_37:
          if ( hMem[0] )
            LocalFree(hMem[0]);
          return v20 != 0;
        }
      }
      else
      {
        Log_HREvent_1((unsigned int)v18, 0, v19, 976);
      }
      v20 = 0;
      goto LABEL_37;
    case 1:
      return v5 == 1;
    case 2:
      if ( *(_DWORD *)(v10 + 3040) == 4 || v5 == 1 || a3 != 1 )
        return v7;
      v13 = a4 == 0;
      goto LABEL_21;
    case 3:
      return 1;
    case 4:
      if ( (_BYTE)a2 )
        return v7;
      v13 = v5 == 1;
LABEL_21:
      if ( v13 )
        return v7;
      return 1;
  }
  v11 = (unsigned int)(a5 - 5);
  if ( a5 == 5 )
  {
    if ( (_BYTE)a2 || v5 != 1 )
      return v7;
    return 1;
  }
  if ( a5 == 6 )
    return a2;
  if ( (unsigned int)dword_180025038 > 4 )
  {
    LODWORD(hMem[0]) = a5;
    v26 = hMem;
    v27 = 4;
    tlgWriteTransfer_EventWriteTransfer((__int64)&dword_180025038, (unsigned __int8 *)&byte_180020B07, 0, 0, 3u, &v25);
  }
  Log_AssertionEvent_2(v11, a2, 696);
  MicrosoftTelemetryAssertTriggeredNoArgs(v12);
  return v7;
}

```

## disassembly

```asm
0x180015020  mov     [rsp-8+arg_10], rbx
0x180015025  push    rbp
0x180015026  push    rsi
0x180015027  push    rdi
0x180015028  push    r12
0x18001502a  push    r13
0x18001502c  push    r14
0x18001502e  push    r15
0x180015030  lea     rbp, [rsp-1B0h]
0x180015038  sub     rsp, 2B0h
0x18001503f  mov     rax, cs:__security_cookie
0x180015046  xor     rax, rsp
0x180015049  mov     [rbp+1E0h+var_40], rax
0x180015050  mov     r14d, [rdx+0CACh]
0x180015057  lea     rsi, [rdx+0BF4h]
0x18001505e  xor     bl, bl
0x180015060  mov     r12d, r9d
0x180015063  cmp     r14d, 1
0x180015067  mov     r13d, r8d
0x18001506a  mov     rdi, rdx
0x18001506d  setz    r15b
0x180015071  cmp     dword ptr [rdx+0BE0h], 4
0x180015078  jnz     short loc_180015095
0x18001507a  movups  xmm0, xmmword ptr [rsi]
0x18001507d  lea     rdx, [rsp+2E0h+hMem]; struct _GUID
0x180015082  movdqu  xmmword ptr [rsp+2E0h+hMem], xmm0
0x180015088  call    ?_AudioEndpointsAvailable@IncomingCallToastStatics@Calls@ApplicationModel@WindowsInternal@@IEAA_NU_GUID@@@Z; WindowsInternal::ApplicationModel::Calls::IncomingCallToastStatics::_AudioEndpointsAvailable(_GUID)
0x18001508d  test    al, al
0x18001508f  jnz     short loc_180015095
0x180015091  mov     dl, 1
0x180015093  jmp     short loc_180015097
0x180015095  xor     dl, dl
0x180015097  mov     r8d, [rbp+1E0h+arg_20]
0x18001509e  mov     ecx, r8d
0x1800150a1  test    r8d, r8d
0x1800150a4  jz      loc_1800151A3
0x1800150aa  sub     ecx, 1
0x1800150ad  jz      loc_18001519B
0x1800150b3  sub     ecx, 1
0x1800150b6  jz      loc_180015175
0x1800150bc  sub     ecx, 1
0x1800150bf  jz      loc_18001516E
0x1800150c5  sub     ecx, 1
0x1800150c8  jz      loc_18001515C
0x1800150ce  sub     ecx, 1
0x1800150d1  jz      short loc_180015148
0x1800150d3  cmp     ecx, 1
0x1800150d6  jz      short loc_180015141
0x1800150d8  mov     eax, cs:dword_180025038
0x1800150de  cmp     eax, 4
0x1800150e1  jbe     short loc_18001512C
0x1800150e3  lea     rax, [rsp+2E0h+hMem]
0x1800150e8  mov     dword ptr [rsp+2E0h+hMem], r8d
0x1800150ed  mov     [rbp+1E0h+var_50], rax
0x1800150f4  lea     rdx, byte_180020B07; int
0x1800150fb  lea     rax, [rbp+1E0h+var_70]
0x180015102  mov     [rbp+1E0h+var_48], 4
0x18001510d  mov     [rsp+2E0h+var_2B8], rax; PEVENT_DATA_DESCRIPTOR
0x180015112  lea     rcx, dword_180025038; int
0x180015119  xor     r9d, r9d; int
0x18001511c  mov     [rsp+2E0h+var_2C0], 3; ULONG
0x180015124  xor     r8d, r8d; int
0x180015127  call    _tlgWriteTransfer_EventWriteTransfer
0x18001512c  mov     r8d, 2B8h
0x180015132  call    Log_AssertionEvent_2
0x180015137  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18001513c  jmp     loc_18001524D
0x180015141  mov     bl, dl
0x180015143  jmp     loc_18001524D
0x180015148  test    dl, dl
0x18001514a  jnz     loc_18001524D
0x180015150  cmp     r14d, 1
0x180015154  jnz     loc_18001524D
0x18001515a  jmp     short loc_18001516E
0x18001515c  test    dl, dl
0x18001515e  jnz     loc_18001524D
0x180015164  cmp     r14d, 1
0x180015168  jz      loc_18001524D
0x18001516e  mov     bl, 1
0x180015170  jmp     loc_18001524D
0x180015175  cmp     dword ptr [rdi+0BE0h], 4
0x18001517c  jz      loc_18001524D
0x180015182  cmp     r14d, 1
0x180015186  jz      loc_18001524D
0x18001518c  cmp     r13d, 1
0x180015190  jnz     loc_18001524D
0x180015196  test    r12d, r12d
0x180015199  jmp     short loc_180015168
0x18001519b  mov     bl, r15b
0x18001519e  jmp     loc_18001524D
0x1800151a3  xor     edx, edx; Val
0x1800151a5  lea     rcx, [rsp+2E0h+var_2A0]; void *
0x1800151aa  mov     r8d, 230h; Size
0x1800151b0  call    memset_0
0x1800151b5  lea     rdx, [rsp+2E0h+var_2A0]
0x1800151ba  mov     rcx, rsi
0x1800151bd  call    cs:__imp_PhoneGetLinePublicInfo
0x1800151c3  test    eax, eax
0x1800151c5  jns     short loc_1800151D8
0x1800151c7  xor     edx, edx
0x1800151c9  mov     r9d, 28Fh
0x1800151cf  mov     ecx, eax
0x1800151d1  call    Log_HREvent_1
0x1800151d6  jmp     short loc_18001524B
0x1800151d8  cmp     dword ptr [rdi+0BE0h], 4
0x1800151df  jnz     short loc_18001524B
0x1800151e1  test    [rbp+1E0h+var_78], 800h
0x1800151eb  jz      short loc_18001524B
0x1800151ed  cmp     dword ptr [rdi+0BDCh], 2
0x1800151f4  jnz     short loc_18001524B
0x1800151f6  add     rdi, 0A0h
0x1800151fd  jz      short loc_18001524B
0x1800151ff  lea     rcx, [rsp+2E0h+hMem]
0x180015204  mov     [rsp+2E0h+hMem], 0
0x18001520d  call    ??$replace@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z$0A@@tlx@@YAPEAPEAGAEAV?$auto_xxx@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z$0A@@0@@Z; tlx::replace<ushort *,void * (*)(void *),&LocalFree(void *),0>(tlx::auto_xxx<ushort *,void * (*)(void *),&LocalFree(void *),0> &)
0x180015212  mov     rdx, rax
0x180015215  mov     rcx, rdi
0x180015218  call    cs:__imp_RemoveMetadataFromNumber
0x18001521e  test    eax, eax
0x180015220  jns     short loc_180015279
0x180015222  xor     edx, edx
0x180015224  mov     r9d, 3D0h
0x18001522a  mov     ecx, eax
0x18001522c  call    Log_HREvent_1
0x180015231  xor     ebx, ebx
0x180015233  mov     rcx, [rsp+2E0h+hMem]; hMem
0x180015238  test    rcx, rcx
0x18001523b  jz      short loc_180015243
0x18001523d  call    cs:__imp_LocalFree
0x180015243  test    ebx, ebx
0x180015245  jnz     loc_18001516E
0x18001524b  xor     bl, bl
0x18001524d  mov     al, bl
0x18001524f  mov     rcx, [rbp+1E0h+var_40]
0x180015256  xor     rcx, rsp; StackCookie
0x180015259  call    __security_check_cookie
0x18001525e  mov     rbx, [rsp+2E0h+arg_10]
0x180015266  add     rsp, 2B0h
0x18001526d  pop     r15
0x18001526f  pop     r14
0x180015271  pop     r13
0x180015273  pop     r12
0x180015275  pop     rdi
0x180015276  pop     rsi
0x180015277  pop     rbp
0x180015278  retn
0x180015279  mov     rcx, [rsp+2E0h+hMem]
0x18001527e  call    cs:__imp_IsNumberDialable
0x180015284  test    eax, eax
0x180015286  jz      short loc_180015231
0x180015288  mov     ebx, 1
0x18001528d  jmp     short loc_180015233
```
