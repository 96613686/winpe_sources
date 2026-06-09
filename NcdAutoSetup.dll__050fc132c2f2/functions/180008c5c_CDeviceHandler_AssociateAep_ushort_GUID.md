# CDeviceHandler::_AssociateAep(ushort *,_GUID *)

- ea: `0x180008c5c`
- end: `0x180008e8a`
- name: `?_AssociateAep@CDeviceHandler@@AEAAJPEAGPEAU_GUID@@@Z`
- size: `558`
- prototype: `__int64 __fastcall(CDeviceHandler *this, unsigned __int16 *, struct _GUID *)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x1800094c8`

## callees

- `0x180008c5c`
- `0x180009f44`
- `0x18000a644`
- `0x18000a778`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008d58`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008d58`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180008d48`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180008d48`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180008dce`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180008dce`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180008e10`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180008e10`
- `deviceassociation!DafSelectCeremony` at `0x180008d09`
- `deviceassociation!DafSelectCeremony` at `0x180008d09`
- `deviceassociation!DafStartFinalize` at `0x180008d95`
- `deviceassociation!DafStartFinalize` at `0x180008d95`
- `deviceassociation!DafCloseAssociationContext` at `0x180008e2a`
- `deviceassociation!DafCloseAssociationContext` at `0x180008e2a`
- `deviceassociation!DafCreateAssociationContext` at `0x180008cbe`
- `deviceassociation!DafCreateAssociationContext` at `0x180008cbe`

## pseudocode

```c
__int64 __fastcall CDeviceHandler::_AssociateAep(CDeviceHandler *this, unsigned __int16 *a2, struct _GUID *a3)
{
  signed int started; // ebx
  _QWORD *v6; // rcx
  __int64 v7; // rdx
  CDeviceHandler *v8; // rcx
  signed int LastError; // eax
  HANDLE hHandle[7]; // [rsp+30h] [rbp-38h] BYREF
  CDeviceHandler *v12; // [rsp+70h] [rbp+8h] BYREF

  v12 = this;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 43, WPP_7fef1fa79ee3391c6a163bc1b1bc3ea3_Traceguids);
  v12 = 0;
  started = DafCreateAssociationContext(a2, 0, 0, 0, &v12);
  if ( started >= 0 )
  {
    started = DafSelectCeremony(v12, DAF_Ceremony_JustWorks);
    if ( started >= 0 )
    {
      hHandle[0] = 0;
      hHandle[1] = CreateEventW(0, 0, 0, 0);
      if ( hHandle[1] )
      {
        CDeviceHandler::_SuppressUX(v8, a3);
        started = DafStartFinalize(v12, &FinalizeCallback, hHandle);
        if ( started >= 0 )
        {
          if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
            WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 46, WPP_7fef1fa79ee3391c6a163bc1b1bc3ea3_Traceguids);
          if ( WaitForSingleObject(hHandle[1], 0x7530u) )
          {
            started = -2147023436;
          }
          else
          {
            started = (signed int)hHandle[0];
            if ( SLODWORD(hHandle[0]) < 0
              && WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
            {
              WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 47, WPP_7fef1fa79ee3391c6a163bc1b1bc3ea3_Traceguids);
            }
          }
        }
        CloseHandle(hHandle[1]);
      }
      else
      {
        LastError = GetLastError();
        started = LastError;
        if ( LastError > 0 )
          started = (unsigned __int16)LastError | 0x80070000;
        if ( started >= 0 )
          started = -2147467259;
      }
      goto LABEL_30;
    }
    v6 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
    {
      v7 = 45;
      goto LABEL_8;
    }
  }
  else
  {
    v6 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
    {
      v7 = 44;
LABEL_8:
      WPP_SF_d(v6[2], v7, WPP_7fef1fa79ee3391c6a163bc1b1bc3ea3_Traceguids);
LABEL_30:
      v6 = WPP_GLOBAL_Control;
    }
  }
  if ( v12 )
  {
    started = DafCloseAssociationContext(v12);
    if ( started >= 0 )
    {
LABEL_36:
      v6 = WPP_GLOBAL_Control;
      goto LABEL_37;
    }
    v6 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
      return (unsigned int)started;
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 48, WPP_7fef1fa79ee3391c6a163bc1b1bc3ea3_Traceguids);
      goto LABEL_36;
    }
  }
LABEL_37:
  if ( v6 != &WPP_GLOBAL_Control && (*((_BYTE *)v6 + 28) & 0x20) != 0 )
    WPP_SF_(v6[2], 49, WPP_7fef1fa79ee3391c6a163bc1b1bc3ea3_Traceguids);
  return (unsigned int)started;
}

```

## disassembly

```asm
0x180008c5c  mov     [rsp+arg_0], rcx
0x180008c61  push    rbx
0x180008c62  push    rbp
0x180008c63  push    rsi
0x180008c64  push    rdi
0x180008c65  sub     rsp, 48h
0x180008c69  mov     rdi, r8
0x180008c6c  mov     rbx, rdx
0x180008c6f  mov     rcx, cs:WPP_GLOBAL_Control
0x180008c76  lea     rsi, WPP_GLOBAL_Control
0x180008c7d  lea     rbp, WPP_7fef1fa79ee3391c6a163bc1b1bc3ea3_Traceguids
0x180008c84  cmp     rcx, rsi
0x180008c87  jz      short loc_180008CA0
0x180008c89  test    byte ptr [rcx+1Ch], 20h
0x180008c8d  jz      short loc_180008CA0
0x180008c8f  mov     rcx, [rcx+10h]
0x180008c93  mov     edx, 2Bh ; '+'
0x180008c98  mov     r8, rbp
0x180008c9b  call    WPP_SF_
0x180008ca0  lea     rax, [rsp+68h+arg_0]
0x180008ca5  mov     [rsp+68h+arg_0], 0
0x180008cae  xor     r9d, r9d
0x180008cb1  mov     [rsp+68h+var_48], rax
0x180008cb6  xor     r8d, r8d
0x180008cb9  xor     edx, edx
0x180008cbb  mov     rcx, rbx
0x180008cbe  call    cs:__imp_DafCreateAssociationContext
0x180008cc4  mov     ebx, eax
0x180008cc6  test    eax, eax
0x180008cc8  jns     short loc_180008CFD
0x180008cca  mov     rcx, cs:WPP_GLOBAL_Control
0x180008cd1  cmp     rcx, rsi
0x180008cd4  jz      loc_180008E1D
0x180008cda  test    byte ptr [rcx+1Ch], 2
0x180008cde  jz      loc_180008E1D
0x180008ce4  mov     edx, 2Ch ; ','
0x180008ce9  mov     rcx, [rcx+10h]
0x180008ced  mov     r9d, eax
0x180008cf0  mov     r8, rbp
0x180008cf3  call    WPP_SF_d
0x180008cf8  jmp     loc_180008E16
0x180008cfd  mov     rcx, [rsp+68h+arg_0]
0x180008d02  lea     rdx, DAF_Ceremony_JustWorks
0x180008d09  call    cs:__imp_DafSelectCeremony
0x180008d0f  mov     ebx, eax
0x180008d11  test    eax, eax
0x180008d13  jns     short loc_180008D36
0x180008d15  mov     rcx, cs:WPP_GLOBAL_Control
0x180008d1c  cmp     rcx, rsi
0x180008d1f  jz      loc_180008E1D
0x180008d25  test    byte ptr [rcx+1Ch], 2
0x180008d29  jz      loc_180008E1D
0x180008d2f  mov     edx, 2Dh ; '-'
0x180008d34  jmp     short loc_180008CE9
0x180008d36  xorps   xmm0, xmm0
0x180008d39  xor     r9d, r9d; lpName
0x180008d3c  xor     r8d, r8d; bInitialState
0x180008d3f  xor     edx, edx; bManualReset
0x180008d41  xor     ecx, ecx; lpEventAttributes
0x180008d43  movups  xmmword ptr [rsp+68h+hHandle], xmm0
0x180008d48  call    cs:__imp_CreateEventW
0x180008d4e  mov     [rsp+68h+hHandle+8], rax
0x180008d53  test    rax, rax
0x180008d56  jnz     short loc_180008D7C
0x180008d58  call    cs:__imp_GetLastError
0x180008d5e  mov     ebx, eax
0x180008d60  test    eax, eax
0x180008d62  jle     short loc_180008D6D
0x180008d64  movzx   ebx, ax
0x180008d67  or      ebx, 80070000h
0x180008d6d  test    ebx, ebx
0x180008d6f  mov     eax, 80004005h
0x180008d74  cmovns  ebx, eax
0x180008d77  jmp     loc_180008E16
0x180008d7c  mov     rdx, rdi; struct _GUID *
0x180008d7f  call    ?_SuppressUX@CDeviceHandler@@AEAAXPEAU_GUID@@@Z; CDeviceHandler::_SuppressUX(_GUID *)
0x180008d84  mov     rcx, [rsp+68h+arg_0]
0x180008d89  lea     r8, [rsp+68h+hHandle]
0x180008d8e  lea     rdx, ?FinalizeCallback@@YAXW4_DAF_ASSOCIATION_STATUS@@PEAXJ@Z; FinalizeCallback(_DAF_ASSOCIATION_STATUS,void *,long)
0x180008d95  call    cs:__imp_DafStartFinalize
0x180008d9b  mov     ebx, eax
0x180008d9d  test    eax, eax
0x180008d9f  js      short loc_180008E0B
0x180008da1  mov     rcx, cs:WPP_GLOBAL_Control
0x180008da8  cmp     rcx, rsi
0x180008dab  jz      short loc_180008DC4
0x180008dad  test    byte ptr [rcx+1Ch], 8
0x180008db1  jz      short loc_180008DC4
0x180008db3  mov     rcx, [rcx+10h]
0x180008db7  mov     edx, 2Eh ; '.'
0x180008dbc  mov     r8, rbp
0x180008dbf  call    WPP_SF_
0x180008dc4  mov     rcx, [rsp+68h+hHandle+8]; hHandle
0x180008dc9  mov     edx, 7530h; dwMilliseconds
0x180008dce  call    cs:__imp_WaitForSingleObject
0x180008dd4  test    eax, eax
0x180008dd6  jnz     short loc_180008E06
0x180008dd8  mov     ebx, dword ptr [rsp+68h+hHandle]
0x180008ddc  test    ebx, ebx
0x180008dde  jns     short loc_180008E0B
0x180008de0  mov     rcx, cs:WPP_GLOBAL_Control
0x180008de7  cmp     rcx, rsi
0x180008dea  jz      short loc_180008E0B
0x180008dec  test    byte ptr [rcx+1Ch], 2
0x180008df0  jz      short loc_180008E0B
0x180008df2  mov     rcx, [rcx+10h]
0x180008df6  lea     edx, [rax+2Fh]
0x180008df9  mov     r9d, ebx
0x180008dfc  mov     r8, rbp
0x180008dff  call    WPP_SF_d
0x180008e04  jmp     short loc_180008E0B
0x180008e06  mov     ebx, 800705B4h
0x180008e0b  mov     rcx, [rsp+68h+hHandle+8]; hObject
0x180008e10  call    cs:__imp_CloseHandle
0x180008e16  mov     rcx, cs:WPP_GLOBAL_Control
0x180008e1d  mov     rax, [rsp+68h+arg_0]
0x180008e22  test    rax, rax
0x180008e25  jz      short loc_180008E63
0x180008e27  mov     rcx, rax
0x180008e2a  call    cs:__imp_DafCloseAssociationContext
0x180008e30  mov     ebx, eax
0x180008e32  test    eax, eax
0x180008e34  jns     short loc_180008E5C
0x180008e36  mov     rcx, cs:WPP_GLOBAL_Control
0x180008e3d  cmp     rcx, rsi
0x180008e40  jz      short loc_180008E7F
0x180008e42  test    byte ptr [rcx+1Ch], 2
0x180008e46  jz      short loc_180008E63
0x180008e48  mov     rcx, [rcx+10h]
0x180008e4c  mov     edx, 30h ; '0'
0x180008e51  mov     r9d, eax
0x180008e54  mov     r8, rbp
0x180008e57  call    WPP_SF_d
0x180008e5c  mov     rcx, cs:WPP_GLOBAL_Control
0x180008e63  cmp     rcx, rsi
0x180008e66  jz      short loc_180008E7F
0x180008e68  test    byte ptr [rcx+1Ch], 20h
0x180008e6c  jz      short loc_180008E7F
0x180008e6e  mov     rcx, [rcx+10h]
0x180008e72  mov     edx, 31h ; '1'
0x180008e77  mov     r8, rbp
0x180008e7a  call    WPP_SF_
0x180008e7f  mov     eax, ebx
0x180008e81  add     rsp, 48h
0x180008e85  pop     rdi
0x180008e86  pop     rsi
0x180008e87  pop     rbp
0x180008e88  pop     rbx
0x180008e89  retn
```
