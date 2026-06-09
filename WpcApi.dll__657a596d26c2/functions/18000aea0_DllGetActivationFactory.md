# DllGetActivationFactory

- ea: `0x18000aea0`
- end: `0x18000b020`
- name: `DllGetActivationFactory`
- size: `384`
- prototype: `__int64 __fastcall(HSTRING string, struct Microsoft::WRL::Details::CreatorMap *)`
- caller_count: `0`
- callee_count: `4`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x1800032a0`
- `0x180007244`
- `0x18000aea0`
- `0x18002c010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18000af0a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18000af0a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsIsStringEmpty` at `0x18000aed6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsIsStringEmpty` at `0x18000aed6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsStringHasEmbeddedNull` at `0x18000aeec`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsStringHasEmbeddedNull` at `0x18000aeec`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateErrorW` at `0x18000aff5`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateErrorW` at `0x18000aff5`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x18000af91`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x18000af91`

## string_xrefs

- `0x18000afbe`: `activatibleClassId`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall DllGetActivationFactory(HSTRING string, struct Microsoft::WRL::Details::CreatorMap *a2)
{
  PCWSTR StringRawBuffer; // r14
  const struct _GUID **v5; // rbx
  unsigned __int64 v6; // rbp
  __int64 v7; // rax
  Microsoft::WRL::Details *v8; // rcx
  __int64 v9; // rax
  int v10; // r8d
  int v11; // edx
  unsigned int v12; // ebx
  BOOL hasEmbedNull; // [rsp+30h] [rbp-58h] BYREF
  int v15; // [rsp+34h] [rbp-54h] BYREF
  __int128 v16; // [rsp+38h] [rbp-50h] BYREF
  _BYTE v17[22]; // [rsp+48h] [rbp-40h]

  *(_QWORD *)a2 = 0;
  hasEmbedNull = 0;
  if ( WindowsIsStringEmpty(string) || WindowsStringHasEmbeddedNull(string, &hasEmbedNull) < 0 || hasEmbedNull )
  {
    v16 = *(_OWORD *)L"activatibleClassId";
    *(_OWORD *)v17 = *(_OWORD *)L"bleClassId";
    *(_QWORD *)&v17[14] = *(_QWORD *)L"sId";
    v12 = -2147024809;
    RoOriginateErrorW(2147942487LL, 18, &v16);
  }
  else
  {
    StringRawBuffer = WindowsGetStringRawBuffer(string, 0);
    v5 = (const struct _GUID **)(((__int64 (__fastcall *)(void ***))WpcDesktop::OTS::ManagerDLL::InProcComServerModule[5])(&WpcDesktop::OTS::ManagerDLL::InProcComServerModule)
                               + 8);
    v6 = ((__int64 (__fastcall *)(void ***))WpcDesktop::OTS::ManagerDLL::InProcComServerModule[6])(&WpcDesktop::OTS::ManagerDLL::InProcComServerModule);
    if ( (unsigned __int64)v5 >= v6 )
    {
LABEL_11:
      v12 = -2147221231;
      RoOriginateError(2147746065LL, string);
    }
    else
    {
      while ( 1 )
      {
        if ( *v5 )
        {
          v7 = (*(__int64 (**)(void))(*v5)->Data4)();
          v8 = (Microsoft::WRL::Details *)StringRawBuffer;
          v9 = v7 - (_QWORD)StringRawBuffer;
          do
          {
            v10 = *(unsigned __int16 *)((char *)v8 + v9);
            v11 = *(unsigned __int16 *)v8 - v10;
            if ( v11 )
              break;
            v8 = (Microsoft::WRL::Details *)((char *)v8 + 2);
          }
          while ( v10 );
          if ( !v11 )
            break;
        }
        if ( (unsigned __int64)++v5 >= v6 )
          goto LABEL_11;
      }
      v15 = 1;
      return (unsigned int)Microsoft::WRL::Details::GetCacheEntry(
                             v8,
                             (struct Microsoft::WRL::Details::ModuleBase *)&v15,
                             &GUID_00000035_0000_0000_c000_000000000046.Data1,
                             *v5,
                             a2);
    }
  }
  return v12;
}

```

## disassembly

```asm
0x18000aea0  mov     [rsp+arg_10], rbx
0x18000aea5  mov     [rsp+arg_18], rbp
0x18000aeaa  push    rsi
0x18000aeab  push    rdi
0x18000aeac  push    r14
0x18000aeae  sub     rsp, 70h
0x18000aeb2  mov     rax, cs:__security_cookie
0x18000aeb9  xor     rax, rsp
0x18000aebc  mov     [rsp+88h+var_28], rax
0x18000aec1  mov     rsi, rdx
0x18000aec4  mov     rdi, rcx
0x18000aec7  mov     qword ptr [rdx], 0
0x18000aece  mov     [rsp+88h+hasEmbedNull], 0
0x18000aed6  call    cs:__imp_WindowsIsStringEmpty
0x18000aedc  test    eax, eax
0x18000aede  jnz     loc_18000AFBE
0x18000aee4  lea     rdx, [rsp+88h+hasEmbedNull]; hasEmbedNull
0x18000aee9  mov     rcx, rdi; string
0x18000aeec  call    cs:__imp_WindowsStringHasEmbeddedNull
0x18000aef2  test    eax, eax
0x18000aef4  js      loc_18000AFBE
0x18000aefa  cmp     [rsp+88h+hasEmbedNull], 1
0x18000aeff  jz      loc_18000AFBE
0x18000af05  xor     edx, edx; length
0x18000af07  mov     rcx, rdi; string
0x18000af0a  call    cs:__imp_WindowsGetStringRawBuffer
0x18000af10  mov     r14, rax
0x18000af13  mov     rcx, cs:?InProcComServerModule@ManagerDLL@OTS@WpcDesktop@@3VWrlModule@WpcBase@@A; WpcBase::WrlModule WpcDesktop::OTS::ManagerDLL::InProcComServerModule
0x18000af1a  mov     rax, [rcx+28h]
0x18000af1e  lea     rcx, ?InProcComServerModule@ManagerDLL@OTS@WpcDesktop@@3VWrlModule@WpcBase@@A; WpcBase::WrlModule WpcDesktop::OTS::ManagerDLL::InProcComServerModule
0x18000af25  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000af2a  lea     rbx, [rax+8]
0x18000af2e  mov     rdx, cs:?InProcComServerModule@ManagerDLL@OTS@WpcDesktop@@3VWrlModule@WpcBase@@A; WpcBase::WrlModule WpcDesktop::OTS::ManagerDLL::InProcComServerModule
0x18000af35  lea     rcx, ?InProcComServerModule@ManagerDLL@OTS@WpcDesktop@@3VWrlModule@WpcBase@@A; WpcBase::WrlModule WpcDesktop::OTS::ManagerDLL::InProcComServerModule
0x18000af3c  mov     rax, [rdx+30h]
0x18000af40  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000af45  mov     rbp, rax
0x18000af48  cmp     rbx, rax
0x18000af4b  jnb     short loc_18000AF87
0x18000af4d  mov     rax, [rbx]
0x18000af50  test    rax, rax
0x18000af53  jz      short loc_18000AF7E
0x18000af55  mov     rax, [rax+8]
0x18000af59  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000af5e  mov     rcx, r14
0x18000af61  sub     rax, r14
0x18000af64  movzx   edx, word ptr [rcx]
0x18000af67  movzx   r8d, word ptr [rcx+rax]
0x18000af6c  sub     edx, r8d
0x18000af6f  jnz     short loc_18000AF7A
0x18000af71  add     rcx, 2; this
0x18000af75  test    r8d, r8d
0x18000af78  jnz     short loc_18000AF64
0x18000af7a  test    edx, edx
0x18000af7c  jz      short loc_18000AF99
0x18000af7e  add     rbx, 8
0x18000af82  cmp     rbx, rbp
0x18000af85  jb      short loc_18000AF4D
0x18000af87  mov     rdx, rdi
0x18000af8a  mov     ebx, 80040111h
0x18000af8f  mov     ecx, ebx
0x18000af91  call    cs:__imp_RoOriginateError
0x18000af97  jmp     short loc_18000AFFC
0x18000af99  mov     [rsp+88h+var_54], 1
0x18000afa1  mov     [rsp+88h+var_68], rsi; struct Microsoft::WRL::Details::CreatorMap *
0x18000afa6  mov     r9, [rbx]; struct _GUID *
0x18000afa9  lea     r8, _GUID_00000035_0000_0000_c000_000000000046; unsigned int *
0x18000afb0  lea     rdx, [rsp+88h+var_54]; struct Microsoft::WRL::Details::ModuleBase *
0x18000afb5  call    ?GetCacheEntry@Details@WRL@Microsoft@@YAJPEAVModuleBase@123@PEAIAEBU_GUID@@PEBUCreatorMap@123@PEAPEAUIUnknown@@@Z; Microsoft::WRL::Details::GetCacheEntry(Microsoft::WRL::Details::ModuleBase *,uint *,_GUID const &,Microsoft::WRL::Details::CreatorMap const *,IUnknown * *)
0x18000afba  mov     ebx, eax
0x18000afbc  jmp     short loc_18000AFFC
0x18000afbe  movups  xmm0, xmmword ptr cs:aActivatiblecla; "activatibleClassId"
0x18000afc5  movups  [rsp+88h+var_50], xmm0
0x18000afca  movups  xmm1, xmmword ptr cs:aActivatiblecla+10h; "bleClassId"
0x18000afd1  movups  xmmword ptr [rsp+88h+var_40], xmm1
0x18000afd6  movsd   xmm0, qword ptr cs:aActivatiblecla+1Eh; "sId"
0x18000afde  movsd   qword ptr [rsp+88h+var_40+0Eh], xmm0
0x18000afe4  lea     r8, [rsp+88h+var_50]
0x18000afe9  mov     edx, 12h
0x18000afee  mov     ebx, 80070057h
0x18000aff3  mov     ecx, ebx
0x18000aff5  call    cs:__imp_RoOriginateErrorW
0x18000affb  nop
0x18000affc  mov     eax, ebx
0x18000affe  mov     rcx, [rsp+88h+var_28]
0x18000b003  xor     rcx, rsp; StackCookie
0x18000b006  call    __security_check_cookie
0x18000b00b  lea     r11, [rsp+88h+var_18]
0x18000b010  mov     rbx, [r11+30h]
0x18000b014  mov     rbp, [r11+38h]
0x18000b018  mov     rsp, r11
0x18000b01b  pop     r14
0x18000b01d  pop     rdi
0x18000b01e  pop     rsi
0x18000b01f  retn
```
