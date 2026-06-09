# Microsoft::Bluetooth::Services::BthServ::BluetoothFindNextService(void *,_BLUETOOTH_SERVICE_RECORD *)

- ea: `0x180022f30`
- end: `0x18002314f`
- name: `?BluetoothFindNextService@BthServ@Services@Bluetooth@Microsoft@@YAHPEAXPEAU_BLUETOOTH_SERVICE_RECORD@@@Z`
- size: `543`
- prototype: `__int64 __fastcall(Microsoft::Bluetooth::Services::BthServ *this, char *, struct _BLUETOOTH_SERVICE_RECORD *)`
- caller_count: `5`
- callee_count: `6`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800237e8`
- `0x180024738`
- `0x1800248ac`
- `0x180024e1c`
- `0x180025e24`

## callees

- `0x1800024ac`
- `0x180022f30`
- `0x180024ca8`
- `0x180025724`
- `0x1800257dc`
- `0x180026308`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180023051`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180023130`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180023051`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180023130`

## pseudocode

```c
__int64 __fastcall Microsoft::Bluetooth::Services::BthServ::BluetoothFindNextService(
        Microsoft::Bluetooth::Services::BthServ *this,
        char *a2,
        struct _BLUETOOTH_SERVICE_RECORD *a3)
{
  unsigned int v3; // ebx
  DWORD v6; // ecx
  Microsoft::Bluetooth::Services::BthServ *v7; // rbp
  unsigned __int64 v8; // r8
  int v9; // eax
  unsigned __int64 v10; // rdx
  unsigned __int32 v11; // ecx
  unsigned __int16 v12; // ax
  __int64 v13; // rax
  unsigned int v14; // edi
  unsigned __int64 v15; // rsi
  unsigned int *v16; // r9
  struct _BLUETOOTH_SDP_RECORD *v17; // rax
  void *v18; // r8
  Microsoft::Bluetooth::Services::BthServ *v19; // rdi
  struct _BLUETOOTH_SDP_RECORD *v20; // rbp
  Microsoft::Bluetooth::Services::BthServ *Record; // rax
  unsigned int v22; // r12d
  unsigned int *v23; // r9
  struct _BLUETOOTH_SDP_RECORD *v24; // r14
  Microsoft::Bluetooth::Services::BthServ *v25; // rcx
  unsigned int v26; // r14d
  bool v27; // zf
  void *v29[7]; // [rsp+20h] [rbp-38h] BYREF
  unsigned int v30; // [rsp+60h] [rbp+8h] BYREF
  Microsoft::Bluetooth::Services::BthServ *v31; // [rsp+70h] [rbp+18h] BYREF

  v3 = 0;
  if ( !this )
  {
    v6 = 6;
LABEL_42:
    SetLastError(v6);
    return v3;
  }
  if ( *(_DWORD *)a2 != 1480 )
  {
    v6 = 1306;
    goto LABEL_42;
  }
  if ( !*((_QWORD *)this + 1) )
  {
    v6 = 259;
    goto LABEL_42;
  }
  v29[0] = (void *)256;
  v29[1] = a2;
  memset_0(a2 + 4, 0, 0x5C4u);
  *(_DWORD *)a2 = 1480;
  v7 = (Microsoft::Bluetooth::Services::BthServ *)*((_QWORD *)this + 1);
  *((_QWORD *)a2 + 1) = v7;
  v8 = *((_QWORD *)this + 1);
  if ( (unsigned __int8)((*(_BYTE *)v8 >> 3) - 6) <= 1u )
  {
    switch ( *(_BYTE *)v8 & 7 )
    {
      case 5:
        v13 = *(unsigned __int8 *)(v8 + 1);
        v10 = v13 + v8 + 2;
        v9 = v13 + 2;
        break;
      case 6:
        v12 = __ROR2__(*(_WORD *)(v8 + 1), 8);
        v10 = v12 + v8 + 3;
        v9 = v12 + 3;
        break;
      case 7:
        v11 = _byteswap_ulong(*(_DWORD *)(v8 + 1));
        v10 = v11 + v8 + 5;
        v9 = v11 + 5;
        break;
      default:
        v10 = 0;
        v9 = 0;
        break;
    }
  }
  else
  {
    v9 = 0;
    v10 = 0;
  }
  v14 = v8 < v10 ? v9 : 0;
  v15 = v10 & -(__int64)(v8 < v10);
  if ( !v15 || v15 == *((_QWORD *)this + 2) )
  {
    v15 = 0;
  }
  else if ( v15 > *((_QWORD *)this + 2) )
  {
    v15 = 0;
    v14 = 0;
  }
  *((_DWORD *)a2 + 4) = v14;
  if ( v14 )
  {
    if ( !v7 )
    {
      v6 = 87;
      goto LABEL_42;
    }
    SetLastError(0xDu);
    if ( (*(_BYTE *)v7 & 0xF8) == 0x30 )
    {
      v30 = 0;
      v17 = Microsoft::Bluetooth::Services::BthServ::BthpInnerRecord(
              v7,
              (Microsoft::Bluetooth::Services::BthServ *)((char *)v7 + v14),
              &v30,
              v16);
      v19 = v17;
      if ( v17 )
      {
        v3 = 1;
        v20 = (struct _BLUETOOTH_SDP_RECORD *)((char *)v17 + v30);
        while ( 1 )
        {
          if ( v19 >= v20 )
            goto LABEL_39;
          Record = Microsoft::Bluetooth::Services::BthServ::BthpNextRecord(v19, v20, v18);
          v22 = (unsigned int)Record;
          if ( !Record )
            break;
          v24 = Microsoft::Bluetooth::Services::BthServ::BthpNextRecord(Record, v20, v18);
          if ( !v24 )
            goto LABEL_38;
          v25 = v19;
          v19 = v24;
          v26 = (_DWORD)v24 - v22;
          if ( v26 >= v30 )
          {
            v3 = 0;
          }
          else
          {
            if ( (*(_BYTE *)v25 & 0xF8) != 8 )
            {
LABEL_38:
              v3 = 0;
              goto LABEL_39;
            }
            LODWORD(v31) = 0;
            if ( !(unsigned int)Microsoft::Bluetooth::Services::BthServ::BthpTransposeAndExtendBytes(
                                  v25,
                                  v20,
                                  &v31,
                                  v23) )
              return 0;
            v27 = Microsoft::Bluetooth::Services::BthServ::BthpNextServiceCallback(
                    (Microsoft::Bluetooth::Services::BthServ *)(unsigned int)v31,
                    v22,
                    (unsigned __int8 *)v26,
                    (unsigned int)v29,
                    v29[0]) == 0;
LABEL_33:
            if ( v27 )
              goto LABEL_39;
          }
        }
        v27 = v19 == 0;
        goto LABEL_33;
      }
    }
LABEL_39:
    if ( v3 )
      *((_QWORD *)this + 1) = v15;
  }
  return v3;
}

```

## disassembly

```asm
0x180022f30  mov     [rsp+arg_8], rbx
0x180022f35  mov     [rsp+arg_18], rbp
0x180022f3a  push    rsi
0x180022f3b  push    rdi
0x180022f3c  push    r12
0x180022f3e  push    r14
0x180022f40  push    r15
0x180022f42  sub     rsp, 30h
0x180022f46  xor     ebx, ebx
0x180022f48  mov     r14, rdx
0x180022f4b  mov     r15, rcx
0x180022f4e  test    rcx, rcx
0x180022f51  jnz     short loc_180022F5B
0x180022f53  lea     ecx, [rbx+6]
0x180022f56  jmp     loc_180023130
0x180022f5b  mov     edi, 5C8h
0x180022f60  cmp     [rdx], edi
0x180022f62  jz      short loc_180022F6E
0x180022f64  mov     ecx, 51Ah
0x180022f69  jmp     loc_180023130
0x180022f6e  cmp     [rcx+8], rbx
0x180022f72  jnz     short loc_180022F7E
0x180022f74  mov     ecx, 103h
0x180022f79  jmp     loc_180023130
0x180022f7e  lea     rcx, [rdx+4]; void *
0x180022f82  mov     [rsp+58h+var_38], 100h; void *
0x180022f8b  xor     edx, edx; Val
0x180022f8d  mov     [rsp+58h+var_30], r14
0x180022f92  mov     r8d, 5C4h; Size
0x180022f98  call    memset_0
0x180022f9d  mov     [r14], edi
0x180022fa0  mov     rbp, [r15+8]
0x180022fa4  mov     [r14+8], rbp
0x180022fa8  mov     r8, [r15+8]
0x180022fac  mov     al, [r8]
0x180022faf  shr     al, 3
0x180022fb2  sub     al, 6
0x180022fb4  cmp     al, 1
0x180022fb6  jbe     short loc_180022FBE
0x180022fb8  xor     eax, eax
0x180022fba  xor     edx, edx
0x180022fbc  jmp     short loc_180023015
0x180022fbe  movzx   ecx, byte ptr [r8]
0x180022fc2  and     ecx, 7
0x180022fc5  sub     ecx, 5
0x180022fc8  jz      short loc_180023006
0x180022fca  sub     ecx, 1
0x180022fcd  jz      short loc_180022FEE
0x180022fcf  cmp     ecx, 1
0x180022fd2  jz      short loc_180022FDA
0x180022fd4  xor     edx, edx
0x180022fd6  xor     eax, eax
0x180022fd8  jmp     short loc_180023015
0x180022fda  mov     ecx, [r8+1]
0x180022fde  lea     rdx, [r8+5]
0x180022fe2  bswap   ecx
0x180022fe4  mov     ecx, ecx
0x180022fe6  add     rdx, rcx
0x180022fe9  lea     eax, [rcx+5]
0x180022fec  jmp     short loc_180023015
0x180022fee  movzx   eax, word ptr [r8+1]
0x180022ff3  lea     rdx, [r8+3]
0x180022ff7  ror     ax, 8
0x180022ffb  movzx   eax, ax
0x180022ffe  add     rdx, rax
0x180023001  add     eax, 3
0x180023004  jmp     short loc_180023015
0x180023006  movzx   eax, byte ptr [r8+1]
0x18002300b  lea     rdx, [r8+2]
0x18002300f  add     rdx, rax
0x180023012  add     eax, 2
0x180023015  cmp     r8, rdx
0x180023018  sbb     edi, edi
0x18002301a  and     edi, eax
0x18002301c  cmp     r8, rdx
0x18002301f  sbb     rsi, rsi
0x180023022  and     rsi, rdx
0x180023025  jz      short loc_180023035
0x180023027  cmp     rsi, [r15+10h]
0x18002302b  jz      short loc_180023035
0x18002302d  jbe     short loc_180023037
0x18002302f  xor     esi, esi
0x180023031  xor     edi, edi
0x180023033  jmp     short loc_180023037
0x180023035  xor     esi, esi
0x180023037  mov     [r14+10h], edi
0x18002303b  test    edi, edi
0x18002303d  jz      loc_180023136
0x180023043  test    rbp, rbp
0x180023046  jz      loc_18002312B
0x18002304c  mov     ecx, 0Dh; dwErrCode
0x180023051  call    cs:__imp_SetLastError
0x180023057  mov     al, [rbp+0]
0x18002305a  and     al, 0F8h
0x18002305c  cmp     al, 30h ; '0'
0x18002305e  jnz     loc_180023121
0x180023064  mov     edx, edi
0x180023066  lea     r8, [rsp+58h+arg_0]; void *
0x18002306b  add     rdx, rbp; struct _BLUETOOTH_SDP_RECORD *
0x18002306e  mov     [rsp+58h+arg_0], ebx
0x180023072  mov     rcx, rbp; this
0x180023075  call    ?BthpInnerRecord@BthServ@Services@Bluetooth@Microsoft@@YAPEAU_BLUETOOTH_SDP_RECORD@@PEAU5@PEAXPEAK@Z; Microsoft::Bluetooth::Services::BthServ::BthpInnerRecord(_BLUETOOTH_SDP_RECORD *,void *,ulong *)
0x18002307a  mov     rdi, rax
0x18002307d  test    rax, rax
0x180023080  jz      loc_180023121
0x180023086  mov     ebp, [rsp+58h+arg_0]
0x18002308a  mov     ebx, 1
0x18002308f  add     rbp, rax
0x180023092  cmp     rdi, rbp
0x180023095  jnb     loc_180023121
0x18002309b  mov     rdx, rbp; struct _BLUETOOTH_SDP_RECORD *
0x18002309e  mov     rcx, rdi; this
0x1800230a1  call    ?BthpNextRecord@BthServ@Services@Bluetooth@Microsoft@@YAPEAU_BLUETOOTH_SDP_RECORD@@PEAU5@PEAX@Z; Microsoft::Bluetooth::Services::BthServ::BthpNextRecord(_BLUETOOTH_SDP_RECORD *,void *)
0x1800230a6  mov     r12, rax
0x1800230a9  test    rax, rax
0x1800230ac  jz      short loc_180023116
0x1800230ae  mov     rdx, rbp; struct _BLUETOOTH_SDP_RECORD *
0x1800230b1  mov     rcx, rax; this
0x1800230b4  call    ?BthpNextRecord@BthServ@Services@Bluetooth@Microsoft@@YAPEAU_BLUETOOTH_SDP_RECORD@@PEAU5@PEAX@Z; Microsoft::Bluetooth::Services::BthServ::BthpNextRecord(_BLUETOOTH_SDP_RECORD *,void *)
0x1800230b9  mov     r14, rax
0x1800230bc  test    rax, rax
0x1800230bf  jz      short loc_18002311F
0x1800230c1  mov     rax, rdi
0x1800230c4  mov     rcx, rdi; this
0x1800230c7  mov     rdi, r14
0x1800230ca  sub     r14d, r12d
0x1800230cd  cmp     r14d, [rsp+58h+arg_0]
0x1800230d2  jnb     short loc_18002310F
0x1800230d4  mov     al, [rcx]
0x1800230d6  and     al, 0F8h
0x1800230d8  cmp     al, 8
0x1800230da  jnz     short loc_18002311F
0x1800230dc  lea     r8, [rsp+58h+arg_10]; void *
0x1800230e1  mov     dword ptr [rsp+58h+arg_10], 0
0x1800230e9  mov     rdx, rbp; struct _BLUETOOTH_SDP_RECORD *
0x1800230ec  call    ?BthpTransposeAndExtendBytes@BthServ@Services@Bluetooth@Microsoft@@YAHPEAU_BLUETOOTH_SDP_RECORD@@PEAXPEAK@Z; Microsoft::Bluetooth::Services::BthServ::BthpTransposeAndExtendBytes(_BLUETOOTH_SDP_RECORD *,void *,ulong *)
0x1800230f1  test    eax, eax
0x1800230f3  jz      short loc_18002311B
0x1800230f5  mov     ecx, dword ptr [rsp+58h+arg_10]; this
0x1800230f9  lea     r9, [rsp+58h+var_38]; unsigned int
0x1800230fe  mov     r8d, r14d; unsigned __int8 *
0x180023101  mov     rdx, r12; unsigned int
0x180023104  call    ?BthpNextServiceCallback@BthServ@Services@Bluetooth@Microsoft@@YAHKPEAEKPEAX@Z; Microsoft::Bluetooth::Services::BthServ::BthpNextServiceCallback(ulong,uchar *,ulong,void *)
0x180023109  test    eax, eax
0x18002310b  jnz     short loc_180023092
0x18002310d  jmp     short loc_180023121
0x18002310f  xor     ebx, ebx
0x180023111  jmp     loc_180023092
0x180023116  test    rdi, rdi
0x180023119  jmp     short loc_18002310B
0x18002311b  xor     ebx, ebx
0x18002311d  jmp     short loc_180023136
0x18002311f  xor     ebx, ebx
0x180023121  test    ebx, ebx
0x180023123  jz      short loc_180023136
0x180023125  mov     [r15+8], rsi
0x180023129  jmp     short loc_180023136
0x18002312b  mov     ecx, 57h ; 'W'; dwErrCode
0x180023130  call    cs:__imp_SetLastError
0x180023136  mov     rbp, [rsp+58h+arg_18]
0x18002313b  mov     eax, ebx
0x18002313d  mov     rbx, [rsp+58h+arg_8]
0x180023142  add     rsp, 30h
0x180023146  pop     r15
0x180023148  pop     r14
0x18002314a  pop     r12
0x18002314c  pop     rdi
0x18002314d  pop     rsi
0x18002314e  retn
```
