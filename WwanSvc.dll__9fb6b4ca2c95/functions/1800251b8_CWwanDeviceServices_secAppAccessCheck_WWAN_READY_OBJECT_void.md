# CWwanDeviceServices::secAppAccessCheck(WWAN_READY_OBJECT *,void *)

- ea: `0x1800251b8`
- end: `0x180025368`
- name: `?secAppAccessCheck@CWwanDeviceServices@@AEAAKPEAUWWAN_READY_OBJECT@@PEAX@Z`
- size: `432`
- prototype: `unsigned int __fastcall(GUID *rguid, struct WWAN_READY_OBJECT *, void *)`
- caller_count: `2`
- callee_count: `6`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x180022470`
- `0x1800635f0`

## callees

- `0x1800085d0`
- `0x1800094f4`
- `0x180012300`
- `0x180014f1c`
- `0x1800251b8`
- `0x1800ae1c8`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x180025272`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x180025272`
- `MobileNetworking!GetNetworkAccountIdBoundToInterfaceId` at `0x180025296`
- `MobileNetworking!GetNetworkAccountIdBoundToInterfaceId` at `0x180025296`
- `MobileNetworking!ValidateNetworkAccountIdBinding` at `0x1800252bd`
- `MobileNetworking!ValidateNetworkAccountIdBinding` at `0x1800252bd`
- `MobileNetworking!GetNetworkAccountBindingDeviceInterfacePath` at `0x1800252d6`
- `MobileNetworking!GetNetworkAccountBindingDeviceInterfacePath` at `0x1800252d6`
- `MobileNetworking!NetworkAccountBindingAccessCheck` at `0x18002530b`
- `MobileNetworking!NetworkAccountBindingAccessCheck` at `0x18002530b`

## string_xrefs

- `0x180025245`: `CWwanDeviceServices::secAppAccessCheck`
- `0x1800252fb`: `CWwanDeviceServices::secAppAccessCheck`
- `0x180025323`: `CWwanDeviceServices::secAppAccessCheck`
- `0x1800252f4`: ` Verifying App access for account %s, device %s`
- `0x18002531a`: `NetworkAccountBindingAccessCheck failed %x`

## pseudocode

```c
__int64 __fastcall CWwanDeviceServices::secAppAccessCheck(GUID *rguid, struct WWAN_READY_OBJECT *a2, void *a3)
{
  unsigned int IsLowBoxClient; // eax
  int NetworkAccountIdBoundToInterfaceId; // ebx
  int v9; // eax
  int v10[4]; // [rsp+30h] [rbp-D0h] BYREF
  OLECHAR sz[40]; // [rsp+40h] [rbp-C0h] BYREF
  _BYTE v12[528]; // [rsp+90h] [rbp-70h] BYREF
  _BYTE v13[528]; // [rsp+2A0h] [rbp+1A0h] BYREF

  memset_0(sz, 0, sizeof(sz));
  memset_0(v12, 0, 0x208u);
  memset_0(v13, 0, 0x208u);
  v10[0] = 0;
  IsLowBoxClient = WwanIsLowBoxClient(v10, a3);
  NetworkAccountIdBoundToInterfaceId = IsLowBoxClient;
  if ( !IsLowBoxClient )
  {
    if ( !v10[0] )
      return 0;
    if ( !StringFromGUID2(rguid, sz, 40) )
    {
      LOWORD(NetworkAccountIdBoundToInterfaceId) = 87;
      return (unsigned __int16)NetworkAccountIdBoundToInterfaceId;
    }
    NetworkAccountIdBoundToInterfaceId = GetNetworkAccountIdBoundToInterfaceId(sz, 260, v12);
    if ( NetworkAccountIdBoundToInterfaceId >= 0 )
    {
      if ( *((_DWORD *)a2 + 28) == -1 )
        return 0;
      NetworkAccountIdBoundToInterfaceId = ValidateNetworkAccountIdBinding(v12, sz, (char *)a2 + 40);
      if ( NetworkAccountIdBoundToInterfaceId >= 0 )
      {
        NetworkAccountIdBoundToInterfaceId = GetNetworkAccountBindingDeviceInterfacePath(v12, 260, v13);
        if ( NetworkAccountIdBoundToInterfaceId >= 0 )
        {
          WwanLog::Info(
            "CWwanDeviceServices::secAppAccessCheck",
            0,
            L" Verifying App access for account %s, device %s",
            v12,
            v13);
          v9 = NetworkAccountBindingAccessCheck(v12);
          NetworkAccountIdBoundToInterfaceId = v9;
          if ( v9 < 0 )
          {
            WwanLog::Error(
              "CWwanDeviceServices::secAppAccessCheck",
              0,
              L"NetworkAccountBindingAccessCheck failed %x",
              (unsigned int)v9);
            goto LABEL_13;
          }
          return 0;
        }
      }
    }
LABEL_13:
    if ( (NetworkAccountIdBoundToInterfaceId & 0x1FFF0000) != 0x70000 )
      return (unsigned int)NetworkAccountIdBoundToInterfaceId;
    return (unsigned __int16)NetworkAccountIdBoundToInterfaceId;
  }
  WwanLog::Error("CWwanDeviceServices::secAppAccessCheck", 0, L"WwanIsLowBoxClient failed %x", IsLowBoxClient);
  return (unsigned int)NetworkAccountIdBoundToInterfaceId;
}

```

## disassembly

```asm
0x1800251b8  mov     [rsp-8+arg_18], rbx
0x1800251bd  push    rbp
0x1800251be  push    rsi
0x1800251bf  push    rdi
0x1800251c0  lea     rbp, [rsp-3C0h]
0x1800251c8  sub     rsp, 4C0h
0x1800251cf  mov     rax, cs:__security_cookie
0x1800251d6  xor     rax, rsp
0x1800251d9  mov     [rbp+3D0h+var_20], rax
0x1800251e0  mov     rdi, rdx
0x1800251e3  mov     rbx, r8
0x1800251e6  xor     edx, edx; Val
0x1800251e8  mov     rsi, rcx
0x1800251eb  lea     rcx, [rsp+4D0h+sz]; void *
0x1800251f0  lea     r8d, [rdx+50h]; Size
0x1800251f4  call    memset_0
0x1800251f9  xor     edx, edx; Val
0x1800251fb  lea     rcx, [rbp+3D0h+var_440]; void *
0x1800251ff  mov     r8d, 208h; Size
0x180025205  call    memset_0
0x18002520a  xor     edx, edx; Val
0x18002520c  lea     rcx, [rbp+3D0h+var_230]; void *
0x180025213  mov     r8d, 208h; Size
0x180025219  call    memset_0
0x18002521e  mov     rdx, rbx; void *
0x180025221  mov     [rsp+4D0h+var_4A0], 0
0x180025229  lea     rcx, [rsp+4D0h+var_4A0]; int *
0x18002522e  call    ?WwanIsLowBoxClient@@YAKPEAHPEAX@Z; WwanIsLowBoxClient(int *,void *)
0x180025233  mov     ebx, eax
0x180025235  test    eax, eax
0x180025237  jz      short loc_180025256
0x180025239  mov     r9d, eax
0x18002523c  lea     r8, aWwanislowboxcl; "WwanIsLowBoxClient failed %x"
0x180025243  xor     edx, edx; struct _GUID *
0x180025245  lea     rcx, aCwwandeviceser_42; "CWwanDeviceServices::secAppAccessCheck"
0x18002524c  call    ?Error@WwanLog@@SAXPEBDPEBU_GUID@@PEBGZZ; WwanLog::Error(char const *,_GUID const *,ushort const *,...)
0x180025251  jmp     loc_180025340
0x180025256  cmp     [rsp+4D0h+var_4A0], 0
0x18002525b  jnz     short loc_180025264
0x18002525d  xor     eax, eax
0x18002525f  jmp     loc_180025342
0x180025264  mov     r8d, 28h ; '('; cchMax
0x18002526a  lea     rdx, [rsp+4D0h+sz]; lpsz
0x18002526f  mov     rcx, rsi; rguid
0x180025272  call    cs:__imp_StringFromGUID2
0x180025278  test    eax, eax
0x18002527a  jnz     short loc_180025286
0x18002527c  mov     ebx, 80070057h
0x180025281  jmp     loc_18002533D
0x180025286  mov     esi, 104h
0x18002528b  lea     r8, [rbp+3D0h+var_440]
0x18002528f  mov     edx, esi
0x180025291  lea     rcx, [rsp+4D0h+sz]
0x180025296  call    cs:__imp_GetNetworkAccountIdBoundToInterfaceId
0x18002529c  mov     ebx, eax
0x18002529e  test    eax, eax
0x1800252a0  js      loc_18002532F
0x1800252a6  cmp     dword ptr [rdi+70h], 0FFFFFFFFh
0x1800252aa  jz      loc_180025364
0x1800252b0  lea     r8, [rdi+28h]
0x1800252b4  lea     rdx, [rsp+4D0h+sz]
0x1800252b9  lea     rcx, [rbp+3D0h+var_440]
0x1800252bd  call    cs:__imp_ValidateNetworkAccountIdBinding
0x1800252c3  mov     ebx, eax
0x1800252c5  test    eax, eax
0x1800252c7  js      short loc_18002532F
0x1800252c9  lea     r8, [rbp+3D0h+var_230]
0x1800252d0  mov     edx, esi
0x1800252d2  lea     rcx, [rbp+3D0h+var_440]
0x1800252d6  call    cs:__imp_GetNetworkAccountBindingDeviceInterfacePath
0x1800252dc  mov     ebx, eax
0x1800252de  test    eax, eax
0x1800252e0  js      short loc_18002532F
0x1800252e2  lea     rax, [rbp+3D0h+var_230]
0x1800252e9  xor     edx, edx; struct _GUID *
0x1800252eb  lea     r9, [rbp+3D0h+var_440]
0x1800252ef  mov     [rsp+4D0h+var_4B0], rax
0x1800252f4  lea     r8, aVerifyingAppAc; " Verifying App access for account %s, d"...
0x1800252fb  lea     rcx, aCwwandeviceser_42; "CWwanDeviceServices::secAppAccessCheck"
0x180025302  call    ?Info@WwanLog@@SAXPEBDPEBU_GUID@@PEBGZZ; WwanLog::Info(char const *,_GUID const *,ushort const *,...)
0x180025307  lea     rcx, [rbp+3D0h+var_440]
0x18002530b  call    cs:__imp_NetworkAccountBindingAccessCheck
0x180025311  mov     ebx, eax
0x180025313  test    eax, eax
0x180025315  jns     short loc_180025364
0x180025317  mov     r9d, eax
0x18002531a  lea     r8, aNetworkaccount_3; "NetworkAccountBindingAccessCheck failed"...
0x180025321  xor     edx, edx; struct _GUID *
0x180025323  lea     rcx, aCwwandeviceser_42; "CWwanDeviceServices::secAppAccessCheck"
0x18002532a  call    ?Error@WwanLog@@SAXPEBDPEBU_GUID@@PEBGZZ; WwanLog::Error(char const *,_GUID const *,ushort const *,...)
0x18002532f  mov     eax, ebx
0x180025331  and     eax, 1FFF0000h
0x180025336  cmp     eax, 70000h
0x18002533b  jnz     short loc_180025340
0x18002533d  movzx   ebx, bx
0x180025340  mov     eax, ebx
0x180025342  mov     rcx, [rbp+3D0h+var_20]
0x180025349  xor     rcx, rsp; StackCookie
0x18002534c  call    __security_check_cookie
0x180025351  mov     rbx, [rsp+4D0h+arg_18]
0x180025359  add     rsp, 4C0h
0x180025360  pop     rdi
0x180025361  pop     rsi
0x180025362  pop     rbp
0x180025363  retn
0x180025364  xor     ebx, ebx
0x180025366  jmp     short loc_180025340
```
