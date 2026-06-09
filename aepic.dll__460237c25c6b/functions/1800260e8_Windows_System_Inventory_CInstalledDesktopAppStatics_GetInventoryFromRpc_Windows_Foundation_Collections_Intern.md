# Windows::System::Inventory::CInstalledDesktopAppStatics::GetInventoryFromRpc(Windows::Foundation::Collections::Internal::Vector<Windows::System::Inventory::InstalledDesktopApp *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::System::Inventory::InstalledDesktopApp *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::System::Inventory::InstalledDesktopApp *>,Windows::Foundation::Collections::Internal::DefaultVectorOptions<Windows::System::Inventory::InstalledDesktopApp *>> *)

- ea: `0x1800260e8`
- end: `0x18002639e`
- name: `?GetInventoryFromRpc@CInstalledDesktopAppStatics@Inventory@System@Windows@@CAJPEAV?$Vector@PEAVInstalledDesktopApp@Inventory@System@Windows@@U?$DefaultEqualityPredicate@PEAVInstalledDesktopApp@Inventory@System@Windows@@@Internal@Collections@Foundation@4@U?$DefaultLifetimeTraits@PEAVInstalledDesktopApp@Inventory@System@Windows@@@6784@U?$DefaultVectorOptions@PEAVInstalledDesktopApp@Inventory@System@Windows@@@6784@@Internal@Collections@Foundation@4@@Z`
- size: `694`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x180025d34`

## callees

- `0x180005890`
- `0x180006938`
- `0x18000c37c`
- `0x1800236d0`
- `0x1800260e8`
- `0x180026b04`
- `0x180027c00`
- `0x180029284`
- `0x1800295dc`
- `0x1800eb010`

## import_xrefs

- `RPCRT4!RpcBindingFree` at `0x18002637a`
- `RPCRT4!RpcBindingFree` at `0x18002637a`
- `RPCRT4!RpcEpResolveBinding` at `0x18002620c`
- `RPCRT4!RpcEpResolveBinding` at `0x18002620c`
- `RPCRT4!RpcStringFreeW` at `0x1800261e7`
- `RPCRT4!RpcStringFreeW` at `0x1800261e7`
- `RPCRT4!RpcBindingFromStringBindingW` at `0x1800261da`
- `RPCRT4!RpcBindingFromStringBindingW` at `0x1800261da`
- `RPCRT4!RpcStringBindingComposeW` at `0x180026173`
- `RPCRT4!RpcStringBindingComposeW` at `0x180026173`

## string_xrefs

- `0x18002633b`: `onecore\base\appcompat\inventory\software\cache\dll\onecore\installeddesktopapp.cpp`
- `0x180026128`: `Windows::System::Inventory::CInstalledDesktopAppStatics::GetInventoryFromRpc`
- `0x18002617f`: `RpcStringBindingCompose failed [%d]`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall Windows::System::Inventory::CInstalledDesktopAppStatics::GetInventoryFromRpc(__int64 a1)
{
  int started; // eax
  int v3; // ebx
  const char *v4; // r9
  __int64 v5; // r8
  Windows::System::Inventory::CInstalledDesktopApp *v6; // rbx
  int v7; // eax
  int v8; // eax
  RPC_WSTR Options; // [rsp+20h] [rbp-E0h]
  int Optionsa; // [rsp+20h] [rbp-E0h]
  RPC_BINDING_HANDLE Binding; // [rsp+30h] [rbp-D0h] BYREF
  RPC_WSTR String; // [rsp+38h] [rbp-C8h] BYREF
  Windows::System::Inventory::CInstalledDesktopApp *v14; // [rsp+40h] [rbp-C0h] BYREF
  unsigned __int16 v15[264]; // [rsp+50h] [rbp-B0h] BYREF
  unsigned __int16 v16[264]; // [rsp+260h] [rbp+160h] BYREF
  unsigned __int16 v17[264]; // [rsp+470h] [rbp+370h] BYREF
  unsigned __int16 v18[264]; // [rsp+680h] [rbp+580h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+8C8h] [rbp+7C8h]

  String = 0;
  Binding = 0;
  started = Windows::Compat::Inventory::RpcHelper::StartInventorySvc();
  if ( started < 0 )
    AslLogCallPrintf(
      3,
      "Windows::System::Inventory::CInstalledDesktopAppStatics::GetInventoryFromRpc",
      293,
      "StartInventorySvc failed %#x",
      started);
  v3 = RpcStringBindingComposeW(0, (RPC_WSTR)L"ncalrpc", 0, 0, 0, &String);
  if ( v3 )
  {
    v4 = "RpcStringBindingCompose failed [%d]";
    v5 = 304;
    goto LABEL_5;
  }
  v3 = RpcBindingFromStringBindingW(String, &Binding);
  RpcStringFreeW(&String);
  if ( v3 )
  {
    v4 = "RpcBindingFromStringBinding failed: [%d]";
    v5 = 313;
    goto LABEL_5;
  }
  v3 = RpcEpResolveBinding(Binding, qword_1800EE790);
  if ( v3 )
  {
    v4 = "RpcEpResolveBinding failed: %d";
    v5 = 321;
LABEL_5:
    LODWORD(Options) = v3;
    AslLogCallPrintf(1, "Windows::System::Inventory::CInstalledDesktopAppStatics::GetInventoryFromRpc", v5, v4, Options);
    if ( v3 > 0 )
      v3 = (unsigned __int16)v3 | 0x80070000;
    goto LABEL_20;
  }
  memset_0(v18, 0, 0x208u);
  memset_0(v17, 0, 0x208u);
  memset_0(v16, 0, 0x208u);
  memset_0(v15, 0, 0x208u);
  v3 = 1;
  do
  {
    if ( !v3 )
    {
      Microsoft::WRL::Details::Make<Windows::System::Inventory::CInstalledDesktopApp,>(&v14);
      v6 = v14;
      if ( v14 )
      {
        Windows::System::Inventory::CInstalledDesktopApp::Initialize(v14, v18, v17, v16, v15);
        v14 = 0;
        v7 = (*(__int64 (__fastcall **)(__int64, Windows::System::Inventory::CInstalledDesktopApp *))(*(_QWORD *)a1 + 104LL))(
               a1,
               v6);
        v3 = v7;
        if ( v7 < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x154,
            (unsigned int)"onecore\\base\\appcompat\\inventory\\software\\cache\\dll\\onecore\\installeddesktopapp.cpp",
            (const char *)(unsigned int)v7,
            Optionsa);
          return (unsigned int)v3;
        }
      }
    }
    v15[0] = 0;
    v16[0] = 0;
    v17[0] = 0;
    v18[0] = 0;
    v8 = Windows::System::Inventory::CInstalledDesktopAppStatics::RpcCall(Binding, v18, v17, v16, v15);
    v3 = v8;
  }
  while ( v8 >= 0 );
  if ( v8 == -2147024637 )
    v3 = 0;
  else
    AslLogCallPrintf(
      1,
      "Windows::System::Inventory::CInstalledDesktopAppStatics::GetInventoryFromRpc",
      354,
      "RAiGetNextAppInfo failed [%#x]",
      v8);
LABEL_20:
  if ( Binding )
    RpcBindingFree(&Binding);
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x1800260e8  push    rbp
0x1800260ea  push    rbx
0x1800260eb  push    rdi
0x1800260ec  push    r14
0x1800260ee  lea     rbp, [rsp-7A8h]
0x1800260f6  sub     rsp, 8A8h
0x1800260fd  mov     rax, cs:__security_cookie
0x180026104  xor     rax, rsp
0x180026107  mov     [rbp+7C0h+var_30], rax
0x18002610e  mov     rdi, rcx
0x180026111  mov     [rsp+8C0h+String], 0
0x18002611a  mov     [rsp+8C0h+Binding], 0
0x180026123  call    ?StartInventorySvc@RpcHelper@Inventory@Compat@Windows@@SAJXZ; Windows::Compat::Inventory::RpcHelper::StartInventorySvc(void)
0x180026128  lea     r14, aWindowsSystemI_2; "Windows::System::Inventory::CInstalledD"...
0x18002612f  test    eax, eax
0x180026131  jns     short loc_180026151
0x180026133  mov     dword ptr [rsp+8C0h+Options], eax
0x180026137  lea     r9, aStartinventory; "StartInventorySvc failed %#x"
0x18002613e  mov     r8d, 125h
0x180026144  mov     rdx, r14
0x180026147  mov     ecx, 3
0x18002614c  call    AslLogCallPrintf
0x180026151  lea     rax, [rsp+8C0h+String]
0x180026156  mov     [rsp+8C0h+StringBinding], rax; StringBinding
0x18002615b  mov     [rsp+8C0h+Options], 0; Options
0x180026164  xor     r9d, r9d; Endpoint
0x180026167  xor     r8d, r8d; NetworkAddr
0x18002616a  lea     rdx, ProtSeq; "ncalrpc"
0x180026171  xor     ecx, ecx; ObjUuid
0x180026173  call    cs:__imp_RpcStringBindingComposeW
0x180026179  mov     ebx, eax
0x18002617b  test    eax, eax
0x18002617d  jz      short loc_1800261D0
0x18002617f  lea     r9, aRpcstringbindi_0; "RpcStringBindingCompose failed [%d]"
0x180026186  mov     r8d, 130h
0x18002618c  mov     dword ptr [rsp+8C0h+Options], ebx
0x180026190  mov     rdx, r14
0x180026193  mov     ecx, 1
0x180026198  call    AslLogCallPrintf
0x18002619d  movzx   edx, bx
0x1800261a0  mov     eax, 80070000h
0x1800261a5  test    ebx, ebx
0x1800261a7  jg      short loc_1800261AD
0x1800261a9  mov     ecx, ebx
0x1800261ab  jmp     short loc_1800261B1
0x1800261ad  mov     ecx, edx
0x1800261af  or      ecx, eax
0x1800261b1  test    ecx, ecx
0x1800261b3  jns     short loc_1800261C6
0x1800261b5  test    ebx, ebx
0x1800261b7  jle     loc_18002636D
0x1800261bd  mov     ebx, edx
0x1800261bf  or      ebx, eax
0x1800261c1  jmp     loc_18002636D
0x1800261c6  mov     ebx, 80004005h
0x1800261cb  jmp     loc_18002636D
0x1800261d0  lea     rdx, [rsp+8C0h+Binding]; Binding
0x1800261d5  mov     rcx, [rsp+8C0h+String]; StringBinding
0x1800261da  call    cs:__imp_RpcBindingFromStringBindingW
0x1800261e0  mov     ebx, eax
0x1800261e2  lea     rcx, [rsp+8C0h+String]; String
0x1800261e7  call    cs:__imp_RpcStringFreeW
0x1800261ed  test    ebx, ebx
0x1800261ef  jz      short loc_180026200
0x1800261f1  lea     r9, aRpcbindingfrom_0; "RpcBindingFromStringBinding failed: [%d"...
0x1800261f8  mov     r8d, 139h
0x1800261fe  jmp     short loc_18002618C
0x180026200  lea     rdx, qword_1800EE790; IfSpec
0x180026207  mov     rcx, [rsp+8C0h+Binding]; Binding
0x18002620c  call    cs:__imp_RpcEpResolveBinding
0x180026212  mov     ebx, eax
0x180026214  test    eax, eax
0x180026216  jz      short loc_18002622A
0x180026218  lea     r9, aRpcepresolvebi_0; "RpcEpResolveBinding failed: %d"
0x18002621f  mov     r8d, 141h
0x180026225  jmp     loc_18002618C
0x18002622a  mov     ebx, 208h
0x18002622f  mov     r8d, ebx; Size
0x180026232  xor     edx, edx; Val
0x180026234  lea     rcx, [rbp+7C0h+var_240]; void *
0x18002623b  call    memset_0
0x180026240  mov     r8d, ebx; Size
0x180026243  xor     edx, edx; Val
0x180026245  lea     rcx, [rbp+7C0h+var_450]; void *
0x18002624c  call    memset_0
0x180026251  mov     r8d, ebx; Size
0x180026254  xor     edx, edx; Val
0x180026256  lea     rcx, [rbp+7C0h+var_660]; void *
0x18002625d  call    memset_0
0x180026262  mov     r8d, ebx; Size
0x180026265  xor     edx, edx; Val
0x180026267  lea     rcx, [rsp+8C0h+var_870]; void *
0x18002626c  call    memset_0
0x180026271  mov     ebx, 1
0x180026276  test    ebx, ebx
0x180026278  jnz     short loc_1800262D7
0x18002627a  lea     rcx, [rsp+8C0h+var_880]
0x18002627f  call    ??$Make@VCInstalledDesktopApp@Inventory@System@Windows@@$$V@Details@WRL@Microsoft@@YA?AV?$ComPtr@VCInstalledDesktopApp@Inventory@System@Windows@@@12@XZ; Microsoft::WRL::Details::Make<Windows::System::Inventory::CInstalledDesktopApp,>(void)
0x180026284  nop
0x180026285  mov     rbx, [rsp+8C0h+var_880]
0x18002628a  test    rbx, rbx
0x18002628d  jz      short loc_1800262D7
0x18002628f  lea     rax, [rsp+8C0h+var_870]
0x180026294  mov     [rsp+8C0h+Options], rax; int
0x180026299  lea     r9, [rbp+7C0h+var_660]; unsigned __int16 *
0x1800262a0  lea     r8, [rbp+7C0h+var_450]; unsigned __int16 *
0x1800262a7  lea     rdx, [rbp+7C0h+var_240]; unsigned __int16 *
0x1800262ae  mov     rcx, rbx; this
0x1800262b1  call    ?Initialize@CInstalledDesktopApp@Inventory@System@Windows@@QEAAXPEBG000@Z; Windows::System::Inventory::CInstalledDesktopApp::Initialize(ushort const *,ushort const *,ushort const *,ushort const *)
0x1800262b6  mov     [rsp+8C0h+var_880], 0
0x1800262bf  mov     rax, [rdi]
0x1800262c2  mov     rdx, rbx
0x1800262c5  mov     rcx, rdi
0x1800262c8  mov     rax, [rax+68h]
0x1800262cc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800262d1  mov     ebx, eax
0x1800262d3  test    eax, eax
0x1800262d5  js      short loc_180026331
0x1800262d7  xor     eax, eax
0x1800262d9  mov     [rsp+8C0h+var_870], ax
0x1800262de  mov     [rbp+7C0h+var_660], ax
0x1800262e5  mov     [rbp+7C0h+var_450], ax
0x1800262ec  mov     [rbp+7C0h+var_240], ax
0x1800262f3  lea     rax, [rsp+8C0h+var_870]
0x1800262f8  mov     [rsp+8C0h+Options], rax; unsigned __int16 *
0x1800262fd  lea     r9, [rbp+7C0h+var_660]; unsigned __int16 *
0x180026304  lea     r8, [rbp+7C0h+var_450]; unsigned __int16 *
0x18002630b  lea     rdx, [rbp+7C0h+var_240]; unsigned __int16 *
0x180026312  mov     rcx, [rsp+8C0h+Binding]; void *
0x180026317  call    ?RpcCall@CInstalledDesktopAppStatics@Inventory@System@Windows@@CAJPEAXPEAG111@Z; Windows::System::Inventory::CInstalledDesktopAppStatics::RpcCall(void *,ushort *,ushort *,ushort *,ushort *)
0x18002631c  mov     ebx, eax
0x18002631e  test    eax, eax
0x180026320  jns     loc_180026276
0x180026326  cmp     eax, 80070103h
0x18002632b  jnz     short loc_18002634F
0x18002632d  xor     ebx, ebx
0x18002632f  jmp     short loc_18002636D
0x180026331  mov     rcx, [rbp+7C8h]; this
0x180026338  mov     r9d, ebx; char *
0x18002633b  lea     r8, aOnecoreBaseApp_2; "onecore\\base\\appcompat\\inventory\\so"...
0x180026342  mov     edx, 154h; void *
0x180026347  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002634c  nop
0x18002634d  jmp     short loc_180026380
0x18002634f  mov     dword ptr [rsp+8C0h+Options], eax
0x180026353  lea     r9, aRaigetnextappi; "RAiGetNextAppInfo failed [%#x]"
0x18002635a  mov     r8d, 162h
0x180026360  mov     rdx, r14
0x180026363  mov     ecx, 1
0x180026368  call    AslLogCallPrintf
0x18002636d  cmp     [rsp+8C0h+Binding], 0
0x180026373  jz      short loc_180026380
0x180026375  lea     rcx, [rsp+8C0h+Binding]; Binding
0x18002637a  call    cs:__imp_RpcBindingFree
0x180026380  mov     eax, ebx
0x180026382  mov     rcx, [rbp+7C0h+var_30]
0x180026389  xor     rcx, rsp; StackCookie
0x18002638c  call    __security_check_cookie
0x180026391  add     rsp, 8A8h
0x180026398  pop     r14
0x18002639a  pop     rdi
0x18002639b  pop     rbx
0x18002639c  pop     rbp
0x18002639d  retn
```
