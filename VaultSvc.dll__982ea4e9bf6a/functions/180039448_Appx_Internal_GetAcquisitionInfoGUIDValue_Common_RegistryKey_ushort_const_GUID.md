# Appx::Internal::GetAcquisitionInfoGUIDValue(Common::RegistryKey *,ushort const *,_GUID *)

- ea: `0x180039448`
- end: `0x180039538`
- name: `?GetAcquisitionInfoGUIDValue@Internal@Appx@@YAJPEAVRegistryKey@Common@@PEBGPEAU_GUID@@@Z`
- size: `240`
- prototype: `__int64 __fastcall(Appx::Internal *this, struct Common::RegistryKey *, struct _GUID *, struct _GUID *)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18002dd0c`

## callees

- `0x180039448`
- `0x180039540`
- `0x1800396b0`
- `0x18003a580`
- `0x18004afcc`

## pseudocode

```c
__int64 __fastcall Appx::Internal::GetAcquisitionInfoGUIDValue(
        Appx::Internal *this,
        struct Common::RegistryKey *a2,
        struct _GUID *a3,
        struct _GUID *a4)
{
  __int64 v5; // rdx
  int AcquisitionInfoStringValue; // ebx
  unsigned int v7; // r8d
  __int64 v8; // rdx
  __int64 result; // rax
  __int64 i; // rax
  unsigned __int64 *v11; // [rsp+20h] [rbp-98h] BYREF
  unsigned __int8 v12[40]; // [rsp+28h] [rbp-90h] BYREF
  BYTE v13[2]; // [rsp+50h] [rbp-68h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+B8h] [rbp+0h]

  v11 = (unsigned __int64 *)39;
  if ( !this || !a3 )
    return 2147942487LL;
  AcquisitionInfoStringValue = Appx::Internal::GetAcquisitionInfoStringValue(
                                 this,
                                 (struct Common::RegistryKey *)L"ConnectedAccountProvider",
                                 v13,
                                 (unsigned __int16 *)&v11,
                                 v11);
  if ( AcquisitionInfoStringValue < 0 )
  {
    v8 = 311;
LABEL_5:
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)v8,
      v7,
      (const char *)(unsigned int)AcquisitionInfoStringValue,
      (int)v11);
    return (unsigned int)AcquisitionInfoStringValue;
  }
  if ( v11 == (unsigned __int64 *)1 )
    return 2147942413LL;
  if ( (_DWORD)v11 != 37 )
  {
LABEL_9:
    AcquisitionInfoStringValue = -2147024885;
LABEL_15:
    v8 = 317;
    goto LABEL_5;
  }
  for ( i = 0; (unsigned int)i < 0x24; i = (unsigned int)(i + 1) )
  {
    v5 = *(unsigned __int16 *)&v13[2 * i];
    v7 = 255;
    if ( (unsigned __int16)v5 > 0xFFu )
      goto LABEL_9;
    v12[i] = v5;
  }
  result = Common::Guid::Decode(v12, v5, a3);
  AcquisitionInfoStringValue = result;
  if ( (int)result < 0 )
    goto LABEL_15;
  return result;
}

```

## disassembly

```asm
0x180039448  mov     [rsp+arg_8], rbx
0x18003944d  push    rdi
0x18003944e  sub     rsp, 0B0h
0x180039455  mov     rax, cs:__security_cookie
0x18003945c  xor     rax, rsp
0x18003945f  mov     [rsp+0B8h+var_18], rax
0x180039467  mov     [rsp+0B8h+var_98], 27h ; '''; int
0x180039470  mov     rdi, r8
0x180039473  test    rcx, rcx
0x180039476  jz      loc_180039512
0x18003947c  test    r8, r8
0x18003947f  jz      loc_180039512
0x180039485  lea     r9, [rsp+0B8h+var_98]; unsigned __int16 *
0x18003948a  lea     r8, [rsp+0B8h+var_68]; LPBYTE
0x18003948f  lea     rdx, aConnectedaccou; "ConnectedAccountProvider"
0x180039496  call    ?GetAcquisitionInfoStringValue@Internal@Appx@@YAJPEAVRegistryKey@Common@@PEBGPEAGPEA_K@Z; Appx::Internal::GetAcquisitionInfoStringValue(Common::RegistryKey *,ushort const *,ushort *,unsigned __int64 *)
0x18003949b  mov     ebx, eax
0x18003949d  test    eax, eax
0x18003949f  jns     short loc_1800394BA
0x1800394a1  mov     edx, 137h; void *
0x1800394a6  mov     rcx, [rsp+0B8h]; this
0x1800394ae  mov     r9d, ebx; char *
0x1800394b1  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800394b6  mov     eax, ebx
0x1800394b8  jmp     short loc_180039517
0x1800394ba  mov     rax, [rsp+0B8h+var_98]
0x1800394bf  sub     rax, 1
0x1800394c3  jnz     short loc_1800394CC
0x1800394c5  mov     eax, 8007000Dh
0x1800394ca  jmp     short loc_180039517
0x1800394cc  cmp     eax, 24h ; '$'
0x1800394cf  jz      short loc_1800394D8
0x1800394d1  mov     ebx, 8007000Bh
0x1800394d6  jmp     short loc_18003950B
0x1800394d8  xor     eax, eax
0x1800394da  cmp     eax, 24h ; '$'
0x1800394dd  jnb     short loc_1800394F8
0x1800394df  movzx   edx, word ptr [rsp+rax*2+0B8h+var_68]
0x1800394e4  mov     r8d, 0FFh
0x1800394ea  cmp     dx, r8w
0x1800394ee  ja      short loc_1800394D1
0x1800394f0  mov     [rsp+rax+0B8h+var_90], dl
0x1800394f4  inc     eax
0x1800394f6  jmp     short loc_1800394DA
0x1800394f8  mov     r8, rdi; struct _GUID *
0x1800394fb  lea     rcx, [rsp+0B8h+var_90]; unsigned __int8 *
0x180039500  call    ?Decode@Guid@Common@@SAJPEBEKPEAU_GUID@@@Z; Common::Guid::Decode(uchar const *,ulong,_GUID *)
0x180039505  mov     ebx, eax
0x180039507  test    eax, eax
0x180039509  jns     short loc_180039517
0x18003950b  mov     edx, 13Dh
0x180039510  jmp     short loc_1800394A6
0x180039512  mov     eax, 80070057h
0x180039517  mov     rcx, [rsp+0B8h+var_18]
0x18003951f  xor     rcx, rsp; StackCookie
0x180039522  call    __security_check_cookie
0x180039527  mov     rbx, [rsp+0B8h+arg_8]
0x18003952f  add     rsp, 0B0h
0x180039536  pop     rdi
0x180039537  retn
```
