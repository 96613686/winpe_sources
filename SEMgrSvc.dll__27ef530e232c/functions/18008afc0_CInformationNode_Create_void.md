# CInformationNode::Create(void)

- ea: `0x18008afc0`
- end: `0x18008b24b`
- name: `?Create@CInformationNode@@QEAAJXZ`
- size: `651`
- prototype: `__int64 __fastcall(CInformationNode *__hidden this)`
- caller_count: `3`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x180089448`
- `0x1800899fc`
- `0x180089ca0`

## callees

- `0x1800049a0`
- `0x180005858`
- `0x18001e61c`
- `0x18008afc0`
- `0x18008b778`
- `0x18009d010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18008b03b`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18008b03b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008b07f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008b0c4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008b21a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008b231`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008b07f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008b0c4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008b21a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008b231`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18008b0d7`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18008b0d7`
- `api-ms-win-devices-swdevice-l1-1-0!SwDeviceClose` at `0x18008b0cf`
- `api-ms-win-devices-swdevice-l1-1-0!SwDeviceClose` at `0x18008b0cf`
- `api-ms-win-devices-swdevice-l1-1-0!SwDeviceCreate` at `0x18008b200`
- `api-ms-win-devices-swdevice-l1-1-0!SwDeviceCreate` at `0x18008b200`

## pseudocode

```c
__int64 __fastcall CInformationNode::Create(CInformationNode *this)
{
  __int64 v2; // rcx
  __int64 *v3; // r15
  unsigned __int8 (__fastcall ***v5)(char *); // r14
  HANDLE EventW; // rdi
  HANDLE v7; // rax
  signed int v8; // eax
  signed int v9; // edi
  __int64 v10; // rsi
  DWORD v11; // ebx
  _QWORD *v12; // rax
  _QWORD *v13; // rax
  _QWORD *v14; // rcx
  bool v15; // cc
  int v16; // eax
  CInformationNode *v17; // rdx
  _QWORD *v18; // rcx
  signed int v19; // eax
  int v20; // edx
  unsigned int v21; // r8d
  signed int LastError; // eax
  int v23; // edx
  unsigned int v24; // r8d
  int v25; // [rsp+40h] [rbp-C0h] BYREF
  _QWORD *v26; // [rsp+48h] [rbp-B8h]
  __int64 v27; // [rsp+50h] [rbp-B0h]
  int v28; // [rsp+68h] [rbp-98h]
  _QWORD *v29; // [rsp+70h] [rbp-90h]
  DEVPROPKEY v30; // [rsp+90h] [rbp-70h] BYREF
  int v31; // [rsp+A4h] [rbp-5Ch]
  int v32; // [rsp+B0h] [rbp-50h]
  int v33; // [rsp+B4h] [rbp-4Ch]
  char *v34; // [rsp+B8h] [rbp-48h]
  DEVPROPGUID fmtid; // [rsp+C0h] [rbp-40h]
  DEVPROPID pid; // [rsp+D0h] [rbp-30h]
  int v37; // [rsp+D4h] [rbp-2Ch]
  int v38; // [rsp+E0h] [rbp-20h]
  int v39; // [rsp+E4h] [rbp-1Ch]
  _QWORD *v40; // [rsp+E8h] [rbp-18h]

  memset_0(&v25, 0, 0x48u);
  memset_0(&v30, 0, 0x60u);
  v3 = (__int64 *)((char *)this + 184);
  if ( *((_QWORD *)this + 23) )
    return 0;
  if ( *((_QWORD *)this + 25) )
    MicrosoftTelemetryAssertTriggeredNoArgs(v2);
  v5 = (unsigned __int8 (__fastcall ***)(char *))((char *)this + 192);
  EventW = CreateEventW(0, 1, 0, 0);
  v7 = (HANDLE)*((_QWORD *)this + 25);
  if ( EventW == v7 )
  {
    EventW = (HANDLE)*((_QWORD *)this + 25);
  }
  else
  {
    if ( v7 && !(**v5)((char *)this + 192) )
    {
      LastError = GetLastError();
      if ( LastError > 0 )
        LastError = (unsigned __int16)LastError | 0x80070000;
      Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)LastError, v23, v24);
      JUMPOUT(0x18008B24ALL);
    }
    *((_QWORD *)this + 25) = EventW;
  }
  if ( !EventW )
  {
    v8 = GetLastError();
    v9 = v8;
    if ( v8 > 0 )
      v9 = (unsigned __int16)v8 | 0x80070000;
LABEL_13:
    if ( v9 < 0 )
    {
      if ( *((_QWORD *)this + 25) )
      {
        if ( !(**v5)((char *)this + 192) )
        {
          v19 = GetLastError();
          if ( v19 > 0 )
            v19 = (unsigned __int16)v19 | 0x80070000;
          Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v19, v20, v21);
          __debugbreak();
        }
        *((_QWORD *)this + 25) = 0;
      }
      v10 = *v3;
      if ( *v3 )
      {
        v11 = GetLastError();
        SwDeviceClose(v10);
        SetLastError(v11);
        *v3 = 0;
      }
    }
    return (unsigned int)v9;
  }
  v12 = (_QWORD *)*((_QWORD *)this + 8);
  v25 = 72;
  if ( v12[3] > 7u )
    v12 = (_QWORD *)*v12;
  v26 = v12;
  v13 = (_QWORD *)((char *)this + 112);
  if ( *((_QWORD *)this + 17) > 7u )
    v13 = (_QWORD *)*v13;
  v29 = v13;
  v14 = (_QWORD *)((char *)this + 32);
  v15 = *((_QWORD *)this + 7) <= 7u;
  v27 = *((_QWORD *)this + 18);
  v30 = DEVPKEY_Device_SessionId;
  v34 = (char *)this + 104;
  v28 = 6;
  v31 = 0;
  v32 = 7;
  v33 = 4;
  if ( !v15 )
    v14 = (_QWORD *)*v14;
  v15 = *((_QWORD *)this + 3) <= 7u;
  pid = DEVPKEY_Device_FriendlyName.pid;
  v16 = *((_DWORD *)this + 12);
  fmtid = DEVPKEY_Device_FriendlyName.fmtid;
  v37 = 0;
  v38 = 18;
  v40 = v14;
  v39 = 2 * v16 + 2;
  if ( v15 )
    v17 = this;
  else
    v17 = *(CInformationNode **)this;
  v18 = (_QWORD *)((char *)this + 152);
  if ( *((_QWORD *)this + 22) > 7u )
    v18 = (_QWORD *)*v18;
  v9 = ((__int64 (__fastcall *)(_QWORD *, CInformationNode *, int *, __int64, DEVPROPKEY *, void (__fastcall *)(struct HSWDEVICE__ *, int, void *, const unsigned __int16 *), CInformationNode *, char *))SwDeviceCreate)(
         v18,
         v17,
         &v25,
         2,
         &v30,
         CInformationNode::_CreateCallback,
         this,
         (char *)this + 184);
  if ( v9 != -2147024713 )
    goto LABEL_13;
  return 0;
}

```

## disassembly

```asm
0x18008afc0  push    rbp
0x18008afc2  push    rbx
0x18008afc3  push    rsi
0x18008afc4  push    rdi
0x18008afc5  push    r14
0x18008afc7  push    r15
0x18008afc9  lea     rbp, [rsp-8]
0x18008afce  sub     rsp, 108h
0x18008afd5  mov     rax, cs:__security_cookie
0x18008afdc  xor     rax, rsp
0x18008afdf  mov     [rbp+30h+var_40], rax
0x18008afe3  xor     edx, edx; Val
0x18008afe5  mov     rbx, rcx
0x18008afe8  lea     rcx, [rsp+130h+var_F0]; void *
0x18008afed  lea     r8d, [rdx+48h]; Size
0x18008aff1  call    memset_0
0x18008aff6  xor     edx, edx; Val
0x18008aff8  lea     rcx, [rbp+30h+var_A0]; void *
0x18008affc  lea     r8d, [rdx+60h]; Size
0x18008b000  call    memset_0
0x18008b005  lea     r15, [rbx+0B8h]
0x18008b00c  cmp     qword ptr [r15], 0
0x18008b010  jz      short loc_18008B019
0x18008b012  xor     eax, eax
0x18008b014  jmp     loc_18008B0E6
0x18008b019  cmp     qword ptr [rbx+0C8h], 0
0x18008b021  jz      short loc_18008B028
0x18008b023  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18008b028  xor     r9d, r9d; lpName
0x18008b02b  lea     r14, [rbx+0C0h]
0x18008b032  xor     r8d, r8d; bInitialState
0x18008b035  xor     ecx, ecx; lpEventAttributes
0x18008b037  lea     edx, [r9+1]; bManualReset
0x18008b03b  call    cs:__imp_CreateEventW
0x18008b041  mov     rdi, rax
0x18008b044  mov     rax, [r14+8]
0x18008b048  cmp     rdi, rax
0x18008b04b  jz      short loc_18008B06E
0x18008b04d  test    rax, rax
0x18008b050  jz      short loc_18008B068
0x18008b052  mov     rax, [r14]
0x18008b055  mov     rcx, r14
0x18008b058  mov     rax, [rax]
0x18008b05b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008b060  test    al, al
0x18008b062  jz      loc_18008B231
0x18008b068  mov     [r14+8], rdi
0x18008b06c  jmp     short loc_18008B071
0x18008b06e  mov     rdi, rax
0x18008b071  mov     esi, 80070000h
0x18008b076  test    rdi, rdi
0x18008b079  jnz     loc_18008B102
0x18008b07f  call    cs:__imp_GetLastError
0x18008b085  mov     edi, eax
0x18008b087  test    eax, eax
0x18008b089  jle     short loc_18008B090
0x18008b08b  movzx   edi, ax
0x18008b08e  or      edi, esi
0x18008b090  test    edi, edi
0x18008b092  jns     short loc_18008B0E4
0x18008b094  cmp     qword ptr [rbx+0C8h], 0
0x18008b09c  jz      short loc_18008B0BC
0x18008b09e  mov     rax, [r14]
0x18008b0a1  mov     rcx, r14
0x18008b0a4  mov     rax, [rax]
0x18008b0a7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008b0ac  test    al, al
0x18008b0ae  jz      loc_18008B21A
0x18008b0b4  mov     qword ptr [r14+8], 0
0x18008b0bc  mov     rsi, [r15]
0x18008b0bf  test    rsi, rsi
0x18008b0c2  jz      short loc_18008B0E4
0x18008b0c4  call    cs:__imp_GetLastError
0x18008b0ca  mov     rcx, rsi
0x18008b0cd  mov     ebx, eax
0x18008b0cf  call    cs:__imp_SwDeviceClose
0x18008b0d5  mov     ecx, ebx; dwErrCode
0x18008b0d7  call    cs:__imp_SetLastError
0x18008b0dd  mov     qword ptr [r15], 0
0x18008b0e4  mov     eax, edi
0x18008b0e6  mov     rcx, [rbp+30h+var_40]
0x18008b0ea  xor     rcx, rsp; StackCookie
0x18008b0ed  call    __security_check_cookie
0x18008b0f2  add     rsp, 108h
0x18008b0f9  pop     r15
0x18008b0fb  pop     r14
0x18008b0fd  pop     rdi
0x18008b0fe  pop     rsi
0x18008b0ff  pop     rbx
0x18008b100  pop     rbp
0x18008b101  retn
0x18008b102  mov     rax, [rbx+40h]
0x18008b106  mov     [rsp+130h+var_F0], 48h ; 'H'
0x18008b10e  cmp     qword ptr [rax+18h], 7
0x18008b113  jbe     short loc_18008B118
0x18008b115  mov     rax, [rax]
0x18008b118  mov     [rsp+130h+var_E8], rax
0x18008b11d  lea     rax, [rbx+70h]
0x18008b121  cmp     qword ptr [rax+18h], 7
0x18008b126  jbe     short loc_18008B12B
0x18008b128  mov     rax, [rax]
0x18008b12b  movups  xmm0, xmmword ptr cs:DEVPKEY_Device_SessionId.fmtid.Data1
0x18008b132  mov     [rsp+130h+var_C0], rax
0x18008b137  lea     rcx, [rbx+20h]
0x18008b13b  cmp     qword ptr [rcx+18h], 7
0x18008b140  mov     rax, [rbx+90h]
0x18008b147  mov     [rsp+130h+var_E0], rax
0x18008b14c  mov     eax, cs:DEVPKEY_Device_SessionId.pid
0x18008b152  mov     [rbp+30h+var_90], eax
0x18008b155  lea     rax, [rbx+68h]
0x18008b159  mov     [rbp+30h+var_78], rax
0x18008b15d  mov     [rsp+130h+var_C8], 6
0x18008b165  movaps  [rbp+30h+var_A0], xmm0
0x18008b169  mov     [rbp+30h+var_8C], 0
0x18008b170  mov     [rbp+30h+var_80], 7
0x18008b177  mov     [rbp+30h+var_7C], 4
0x18008b17e  jbe     short loc_18008B183
0x18008b180  mov     rcx, [rcx]
0x18008b183  cmp     qword ptr [rbx+18h], 7
0x18008b188  mov     eax, cs:DEVPKEY_Device_FriendlyName.pid
0x18008b18e  movups  xmm0, xmmword ptr cs:DEVPKEY_Device_FriendlyName.fmtid.Data1
0x18008b195  mov     [rbp+30h+var_60], eax
0x18008b198  mov     eax, [rbx+30h]
0x18008b19b  movaps  [rbp+30h+var_70], xmm0
0x18008b19f  mov     [rbp+30h+var_5C], 0
0x18008b1a6  mov     [rbp+30h+var_50], 12h
0x18008b1ad  lea     eax, ds:2[rax*2]
0x18008b1b4  mov     [rbp+30h+var_48], rcx
0x18008b1b8  mov     [rbp+30h+var_4C], eax
0x18008b1bb  jbe     short loc_18008B1C2
0x18008b1bd  mov     rdx, [rbx]
0x18008b1c0  jmp     short loc_18008B1C5
0x18008b1c2  mov     rdx, rbx
0x18008b1c5  lea     rcx, [rbx+98h]
0x18008b1cc  cmp     qword ptr [rcx+18h], 7
0x18008b1d1  jbe     short loc_18008B1D6
0x18008b1d3  mov     rcx, [rcx]
0x18008b1d6  mov     [rsp+130h+var_F8], r15
0x18008b1db  lea     rax, ?_CreateCallback@CInformationNode@@CAXPEAUHSWDEVICE__@@JPEAXPEBG@Z; CInformationNode::_CreateCallback(HSWDEVICE__ *,long,void *,ushort const *)
0x18008b1e2  mov     [rsp+130h+var_100], rbx
0x18008b1e7  lea     r8, [rsp+130h+var_F0]
0x18008b1ec  mov     [rsp+130h+var_108], rax
0x18008b1f1  mov     r9d, 2
0x18008b1f7  lea     rax, [rbp+30h+var_A0]
0x18008b1fb  mov     [rsp+130h+var_110], rax
0x18008b200  call    cs:__imp_SwDeviceCreate
0x18008b206  mov     edi, eax
0x18008b208  cmp     eax, 800700B7h
0x18008b20d  jnz     loc_18008B090
0x18008b213  xor     edi, edi
0x18008b215  jmp     loc_18008B0E4
0x18008b21a  call    cs:__imp_GetLastError
0x18008b220  test    eax, eax
0x18008b222  jle     short loc_18008B229
0x18008b224  movzx   eax, ax
0x18008b227  or      eax, esi
0x18008b229  mov     ecx, eax; this
0x18008b22b  call    ?RaiseException@Details@WRL@Microsoft@@YAXJK@Z; Microsoft::WRL::Details::RaiseException(long,ulong)
0x18008b230  int     3; Trap to Debugger
0x18008b231  call    cs:__imp_GetLastError
0x18008b237  test    eax, eax
0x18008b239  jle     short loc_18008B243
0x18008b23b  movzx   eax, ax
0x18008b23e  or      eax, 80070000h
0x18008b243  mov     ecx, eax; this
0x18008b245  call    ?RaiseException@Details@WRL@Microsoft@@YAXJK@Z; Microsoft::WRL::Details::RaiseException(long,ulong)
```
