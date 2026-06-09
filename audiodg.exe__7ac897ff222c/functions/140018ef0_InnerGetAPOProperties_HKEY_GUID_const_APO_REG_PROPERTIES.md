# InnerGetAPOProperties(HKEY__ *,_GUID const &,APO_REG_PROPERTIES *)

- ea: `0x140018ef0`
- end: `0x14001906e`
- name: `?InnerGetAPOProperties@@YAJPEAUHKEY__@@AEBU_GUID@@PEAUAPO_REG_PROPERTIES@@@Z`
- size: `382`
- prototype: `__int64 __fastcall(HKEY hKey, const struct _GUID *, struct APO_REG_PROPERTIES *)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x140018d0c`

## callees

- `0x140018ef0`
- `0x140019080`
- `0x14005d0e0`
- `0x14005e168`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x140018f8c`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x140018f8c`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x140018faa`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x140018faa`

## pseudocode

```c
LSTATUS __fastcall InnerGetAPOProperties(HKEY hKey, const struct _GUID *a2, struct APO_REG_PROPERTIES *a3)
{
  LSTATUS result; // eax
  LSTATUS v7; // edx
  APO_REG_PROPERTIES *v8; // rcx
  __int64 v9; // rax
  CLSID clsid; // xmm0
  __int128 v11; // xmm1
  __int128 v12; // xmm0
  __int128 v13; // xmm1
  __int128 v14; // xmm0
  __int128 v15; // xmm1
  __int128 v16; // xmm0
  IID v17; // xmm1
  int v18; // eax
  __int128 v19; // xmm1
  __int128 v20; // xmm0
  __int128 v21; // xmm1
  DWORD pcbData[4]; // [rsp+40h] [rbp-878h] BYREF
  APO_REG_PROPERTIES v23; // [rsp+50h] [rbp-868h] BYREF
  OLECHAR sz[512]; // [rsp+4A0h] [rbp-418h] BYREF

  memset_0(&v23, 0, sizeof(v23));
  result = InnerGetCommon(hKey, a2, &v23);
  if ( result >= 0 )
  {
    v23.u32NumAPOInterfaces = 1;
    pcbData[0] = 1024;
    result = RegGetValueW(hKey, 0, L"APOInterface0", 2u, 0, sz, pcbData);
    if ( result )
    {
      if ( result > 0 )
        return (unsigned __int16)result | 0x80070000;
    }
    else
    {
      result = CLSIDFromString(sz, v23.iidAPOInterfaceList);
      v7 = result;
      if ( result >= 0 )
      {
        v8 = &v23;
        v9 = 8;
        do
        {
          a3 = (struct APO_REG_PROPERTIES *)((char *)a3 + 128);
          clsid = v8->clsid;
          v11 = *(_OWORD *)&v8->Flags;
          v8 = (APO_REG_PROPERTIES *)((char *)v8 + 128);
          *(CLSID *)&a3[-1].szCopyrightInfo[216] = clsid;
          v12 = *(_OWORD *)&v8[-1].szCopyrightInfo[232];
          *(_OWORD *)&a3[-1].szCopyrightInfo[224] = v11;
          v13 = *(_OWORD *)&v8[-1].szCopyrightInfo[240];
          *(_OWORD *)&a3[-1].szCopyrightInfo[232] = v12;
          v14 = *(_OWORD *)&v8[-1].szCopyrightInfo[248];
          *(_OWORD *)&a3[-1].szCopyrightInfo[240] = v13;
          v15 = *(_OWORD *)&v8[-1].u32MajorVersion;
          *(_OWORD *)&a3[-1].szCopyrightInfo[248] = v14;
          v16 = *(_OWORD *)&v8[-1].u32MinOutputConnections;
          *(_OWORD *)&a3[-1].u32MajorVersion = v15;
          v17 = v8[-1].iidAPOInterfaceList[0];
          *(_OWORD *)&a3[-1].u32MinOutputConnections = v16;
          a3[-1].iidAPOInterfaceList[0] = v17;
          --v9;
        }
        while ( v9 );
        v18 = *(_DWORD *)&v8->szFriendlyName[22];
        v19 = *(_OWORD *)&v8->Flags;
        a3->clsid = v8->clsid;
        v20 = *(_OWORD *)&v8->szFriendlyName[6];
        *(_OWORD *)&a3->Flags = v19;
        v21 = *(_OWORD *)&v8->szFriendlyName[14];
        *(_OWORD *)&a3->szFriendlyName[6] = v20;
        *(_OWORD *)&a3->szFriendlyName[14] = v21;
        *(_DWORD *)&a3->szFriendlyName[22] = v18;
        return v7;
      }
    }
  }
  return result;
}

```

## disassembly

```asm
0x140018ef0  mov     [rsp+arg_8], rbx
0x140018ef5  mov     [rsp+arg_18], rsi
0x140018efa  push    rdi
0x140018efb  sub     rsp, 8B0h
0x140018f02  mov     rax, cs:__security_cookie
0x140018f09  xor     rax, rsp
0x140018f0c  mov     [rsp+8B8h+var_18], rax
0x140018f14  mov     rdi, r8
0x140018f17  mov     rbx, rdx
0x140018f1a  mov     rsi, rcx
0x140018f1d  xor     edx, edx; Val
0x140018f1f  mov     r8d, 444h; Size
0x140018f25  lea     rcx, [rsp+8B8h+var_868]; void *
0x140018f2a  call    memset_0
0x140018f2f  lea     r8, [rsp+8B8h+var_868]; struct APO_REG_PROPERTIES *
0x140018f34  mov     rdx, rbx; struct _GUID *
0x140018f37  mov     rcx, rsi; hKey
0x140018f3a  call    ?InnerGetCommon@@YAJPEAUHKEY__@@AEBU_GUID@@PEAUAPO_REG_PROPERTIES@@@Z; InnerGetCommon(HKEY__ *,_GUID const &,APO_REG_PROPERTIES *)
0x140018f3f  test    eax, eax
0x140018f41  js      loc_14001903D
0x140018f47  lea     rax, [rsp+8B8h+var_878]
0x140018f4c  mov     [rsp+8B8h+var_868.u32NumAPOInterfaces], 1
0x140018f57  mov     [rsp+8B8h+pcbData], rax; pcbData
0x140018f5c  lea     r8, Value; "APOInterface0"
0x140018f63  lea     rax, [rsp+8B8h+sz]
0x140018f6b  mov     [rsp+8B8h+var_878], 400h
0x140018f73  mov     [rsp+8B8h+pvData], rax; pvData
0x140018f78  mov     r9d, 2; dwFlags
0x140018f7e  xor     edx, edx; lpSubKey
0x140018f80  mov     [rsp+8B8h+pdwType], 0; pdwType
0x140018f89  mov     rcx, rsi; hkey
0x140018f8c  call    cs:__imp_RegGetValueW
0x140018f92  test    eax, eax
0x140018f94  jnz     loc_140019062
0x140018f9a  lea     rdx, [rsp+8B8h+var_868.iidAPOInterfaceList]; pclsid
0x140018fa2  lea     rcx, [rsp+8B8h+sz]; lpsz
0x140018faa  call    cs:__imp_CLSIDFromString
0x140018fb0  mov     edx, eax
0x140018fb2  test    eax, eax
0x140018fb4  js      loc_14001903D
0x140018fba  lea     rcx, [rsp+8B8h+var_868]
0x140018fbf  mov     eax, 8
0x140018fc4  lea     rdi, [rdi+80h]
0x140018fcb  movups  xmm0, xmmword ptr [rcx]
0x140018fce  movups  xmm1, xmmword ptr [rcx+10h]
0x140018fd2  lea     rcx, [rcx+80h]
0x140018fd9  movups  xmmword ptr [rdi-80h], xmm0
0x140018fdd  movups  xmm0, xmmword ptr [rcx-60h]
0x140018fe1  movups  xmmword ptr [rdi-70h], xmm1
0x140018fe5  movups  xmm1, xmmword ptr [rcx-50h]
0x140018fe9  movups  xmmword ptr [rdi-60h], xmm0
0x140018fed  movups  xmm0, xmmword ptr [rcx-40h]
0x140018ff1  movups  xmmword ptr [rdi-50h], xmm1
0x140018ff5  movups  xmm1, xmmword ptr [rcx-30h]
0x140018ff9  movups  xmmword ptr [rdi-40h], xmm0
0x140018ffd  movups  xmm0, xmmword ptr [rcx-20h]
0x140019001  movups  xmmword ptr [rdi-30h], xmm1
0x140019005  movups  xmm1, xmmword ptr [rcx-10h]
0x140019009  movups  xmmword ptr [rdi-20h], xmm0
0x14001900d  movups  xmmword ptr [rdi-10h], xmm1
0x140019011  sub     rax, 1
0x140019015  jnz     short loc_140018FC4
0x140019017  movups  xmm0, xmmword ptr [rcx]
0x14001901a  mov     eax, [rcx+40h]
0x14001901d  movups  xmm1, xmmword ptr [rcx+10h]
0x140019021  movups  xmmword ptr [rdi], xmm0
0x140019024  movups  xmm0, xmmword ptr [rcx+20h]
0x140019028  movups  xmmword ptr [rdi+10h], xmm1
0x14001902c  movups  xmm1, xmmword ptr [rcx+30h]
0x140019030  movups  xmmword ptr [rdi+20h], xmm0
0x140019034  movups  xmmword ptr [rdi+30h], xmm1
0x140019038  mov     [rdi+40h], eax
0x14001903b  mov     eax, edx
0x14001903d  mov     rcx, [rsp+8B8h+var_18]
0x140019045  xor     rcx, rsp; StackCookie
0x140019048  call    __security_check_cookie
0x14001904d  lea     r11, [rsp+8B8h+var_8]
0x140019055  mov     rbx, [r11+18h]
0x140019059  mov     rsi, [r11+28h]
0x14001905d  mov     rsp, r11
0x140019060  pop     rdi
0x140019061  retn
0x140019062  jle     short loc_14001903D
0x140019064  movzx   eax, ax
0x140019067  or      eax, 80070000h
0x14001906c  jmp     short loc_14001903D
```
