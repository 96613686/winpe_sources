# CxspRegisterWlanNotification(_GIP_WLAN_CLIENT *,void (*)(_L2_NOTIFICATION_DATA *,void *),void *)

- ea: `0x18000ac68`
- end: `0x18000adea`
- name: `?CxspRegisterWlanNotification@@YAKPEAU_GIP_WLAN_CLIENT@@P6AXPEAU_L2_NOTIFICATION_DATA@@PEAX@Z2@Z`
- size: `386`
- prototype: `__int64 __fastcall(void **, void (*)(struct _L2_NOTIFICATION_DATA *, void *), void *)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x18000a1b4`

## callees

- `0x180002b48`
- `0x180002b70`
- `0x18000a600`
- `0x18000ac68`
- `0x18000ba20`

## import_xrefs

- `wlanapi!WlanCloseHandle` at `0x18000ad7a`
- `wlanapi!WlanCloseHandle` at `0x18000ad7a`
- `wlanapi!WlanRegisterNotification` at `0x18000ad34`
- `wlanapi!WlanRegisterNotification` at `0x18000ad34`
- `wlanapi!WlanOpenHandle` at `0x18000ac91`
- `wlanapi!WlanOpenHandle` at `0x18000ac91`

## pseudocode

```c
__int64 __fastcall CxspRegisterWlanNotification(
        void **a1,
        void (*a2)(struct _L2_NOTIFICATION_DATA *, void *),
        void *a3)
{
  HANDLE *v3; // rdi
  DWORD v5; // eax
  DWORD v6; // esi
  _QWORD *v7; // rcx
  __int64 v8; // rdx
  DWORD pdwNegotiatedVersion; // [rsp+78h] [rbp+10h] BYREF
  int v11; // [rsp+7Ch] [rbp+14h]

  v11 = HIDWORD(a2);
  v3 = a1 + 8;
  pdwNegotiatedVersion = 0;
  v5 = WlanOpenHandle(2u, 0, &pdwNegotiatedVersion, a1 + 8);
  v6 = v5;
  if ( v5 )
  {
    v7 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) )
    {
      v8 = 26;
LABEL_15:
      WPP_SF_D(v7[2], v8, &WPP_4b7fc9b143d0368172f607d8a9267014_Traceguids, v5);
      goto LABEL_16;
    }
    goto LABEL_16;
  }
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 2), 27);
  }
  CxsWlanNotification(0, a3);
  v5 = WlanRegisterNotification(*v3, 8u, 0, CxsWlanNotification, a3, 0, 0);
  v6 = v5;
  if ( v5 )
  {
    v7 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) )
    {
      v8 = 28;
      goto LABEL_15;
    }
LABEL_16:
    if ( *v3 )
    {
      WlanCloseHandle(*v3, 0);
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
      {
        WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 2), 30);
      }
      *v3 = 0;
    }
    return v6;
  }
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 29, &WPP_4b7fc9b143d0368172f607d8a9267014_Traceguids);
  }
  return v6;
}

```

## disassembly

```asm
0x18000ac68  mov     qword ptr [rsp+pdwNegotiatedVersion], rdx
0x18000ac6d  push    rbx
0x18000ac6e  push    rbp
0x18000ac6f  push    rsi
0x18000ac70  push    rdi
0x18000ac71  sub     rsp, 48h
0x18000ac75  lea     rdi, [rcx+40h]
0x18000ac79  mov     [rsp+68h+pdwNegotiatedVersion], 0
0x18000ac81  xor     edx, edx; pReserved
0x18000ac83  mov     rbp, r8
0x18000ac86  mov     r9, rdi; phClientHandle
0x18000ac89  lea     r8, [rsp+68h+pdwNegotiatedVersion]; pdwNegotiatedVersion
0x18000ac8e  lea     ecx, [rdx+2]; dwClientVersion
0x18000ac91  call    cs:__imp_WlanOpenHandle
0x18000ac97  mov     esi, eax
0x18000ac99  test    eax, eax
0x18000ac9b  jz      short loc_18000ACD2
0x18000ac9d  mov     rcx, cs:WPP_GLOBAL_Control
0x18000aca4  lea     rbx, WPP_GLOBAL_Control
0x18000acab  cmp     rcx, rbx
0x18000acae  jz      loc_18000AD70
0x18000acb4  test    byte ptr [rcx+1Ch], 4
0x18000acb8  jz      loc_18000AD70
0x18000acbe  cmp     byte ptr [rcx+19h], 1
0x18000acc2  jb      loc_18000AD70
0x18000acc8  mov     edx, 1Ah
0x18000accd  jmp     loc_18000AD5D
0x18000acd2  mov     rcx, cs:WPP_GLOBAL_Control
0x18000acd9  lea     rbx, WPP_GLOBAL_Control
0x18000ace0  cmp     rcx, rbx
0x18000ace3  jz      short loc_18000AD02
0x18000ace5  test    byte ptr [rcx+1Ch], 4
0x18000ace9  jz      short loc_18000AD02
0x18000aceb  cmp     byte ptr [rcx+19h], 5
0x18000acef  jb      short loc_18000AD02
0x18000acf1  mov     r9, [rdi]
0x18000acf4  mov     edx, 1Bh
0x18000acf9  mov     rcx, [rcx+10h]
0x18000acfd  call    WPP_SF_q
0x18000ad02  mov     rdx, rbp; PVOID
0x18000ad05  xor     ecx, ecx; PWLAN_NOTIFICATION_DATA
0x18000ad07  call    ?CxsWlanNotification@@YAXPEAU_L2_NOTIFICATION_DATA@@PEAX@Z; CxsWlanNotification(_L2_NOTIFICATION_DATA *,void *)
0x18000ad0c  mov     rcx, [rdi]; hClientHandle
0x18000ad0f  lea     r9, ?CxsWlanNotification@@YAXPEAU_L2_NOTIFICATION_DATA@@PEAX@Z; funcCallback
0x18000ad16  xor     r8d, r8d; bIgnoreDuplicate
0x18000ad19  mov     [rsp+68h+pdwPrevNotifSource], 0; pdwPrevNotifSource
0x18000ad22  mov     [rsp+68h+pReserved], 0; pReserved
0x18000ad2b  mov     [rsp+68h+pCallbackContext], rbp; pCallbackContext
0x18000ad30  lea     edx, [r8+8]; dwNotifSource
0x18000ad34  call    cs:__imp_WlanRegisterNotification
0x18000ad3a  mov     esi, eax
0x18000ad3c  test    eax, eax
0x18000ad3e  jz      short loc_18000ADB2
0x18000ad40  mov     rcx, cs:WPP_GLOBAL_Control
0x18000ad47  cmp     rcx, rbx
0x18000ad4a  jz      short loc_18000AD70
0x18000ad4c  test    byte ptr [rcx+1Ch], 4
0x18000ad50  jz      short loc_18000AD70
0x18000ad52  cmp     byte ptr [rcx+19h], 1
0x18000ad56  jb      short loc_18000AD70
0x18000ad58  mov     edx, 1Ch
0x18000ad5d  mov     rcx, [rcx+10h]
0x18000ad61  lea     r8, WPP_4b7fc9b143d0368172f607d8a9267014_Traceguids
0x18000ad68  mov     r9d, eax
0x18000ad6b  call    WPP_SF_D
0x18000ad70  mov     rcx, [rdi]; hClientHandle
0x18000ad73  test    rcx, rcx
0x18000ad76  jz      short loc_18000ADDF
0x18000ad78  xor     edx, edx; pReserved
0x18000ad7a  call    cs:__imp_WlanCloseHandle
0x18000ad80  mov     rcx, cs:WPP_GLOBAL_Control
0x18000ad87  cmp     rcx, rbx
0x18000ad8a  jz      short loc_18000ADA9
0x18000ad8c  test    byte ptr [rcx+1Ch], 4
0x18000ad90  jz      short loc_18000ADA9
0x18000ad92  cmp     byte ptr [rcx+19h], 5
0x18000ad96  jb      short loc_18000ADA9
0x18000ad98  mov     r9, [rdi]
0x18000ad9b  mov     edx, 1Eh
0x18000ada0  mov     rcx, [rcx+10h]
0x18000ada4  call    WPP_SF_q
0x18000ada9  mov     qword ptr [rdi], 0
0x18000adb0  jmp     short loc_18000ADDF
0x18000adb2  mov     rcx, cs:WPP_GLOBAL_Control
0x18000adb9  cmp     rcx, rbx
0x18000adbc  jz      short loc_18000ADDF
0x18000adbe  test    byte ptr [rcx+1Ch], 4
0x18000adc2  jz      short loc_18000ADDF
0x18000adc4  cmp     byte ptr [rcx+19h], 4
0x18000adc8  jb      short loc_18000ADDF
0x18000adca  mov     rcx, [rcx+10h]
0x18000adce  lea     r8, WPP_4b7fc9b143d0368172f607d8a9267014_Traceguids
0x18000add5  mov     edx, 1Dh
0x18000adda  call    WPP_SF_
0x18000addf  mov     eax, esi
0x18000ade1  add     rsp, 48h
0x18000ade5  pop     rdi
0x18000ade6  pop     rsi
0x18000ade7  pop     rbp
0x18000ade8  pop     rbx
0x18000ade9  retn
```
