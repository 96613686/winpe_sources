# CWMIBinMof::BinaryMofEventChanged(_WNODE_HEADER *)

- ea: `0x1800066b4`
- end: `0x180006890`
- name: `?BinaryMofEventChanged@CWMIBinMof@@QEAAHPEAU_WNODE_HEADER@@@Z`
- size: `476`
- prototype: `int(CWMIBinMof *__hidden this, struct _WNODE_HEADER *)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x1800065e0`

## callees

- `0x1800066b4`
- `0x180006898`
- `0x180006bb0`
- `0x18001a268`
- `0x18001d36b`
- `0x18001d3a0`

## import_xrefs

- `wbemcomn!DebugTrace` at `0x180006789`
- `wbemcomn!DebugTrace` at `0x1800067a5`
- `wbemcomn!DebugTrace` at `0x180006789`
- `wbemcomn!DebugTrace` at `0x1800067a5`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x1800066ed`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x1800066ed`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x180006741`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x18000676d`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x180006741`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x18000676d`

## string_xrefs

- `0x180006857`: `RuntimeBinaryMofsDeleted`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CWMIBinMof::BinaryMofEventChanged(CWMIBinMof *this, struct _WNODE_HEADER *a2)
{
  unsigned int v4; // edi
  CWMIStandardShell *v5; // rax
  CWMIStandardShell *v6; // rbx
  __int64 v7; // rax
  const char *v8; // rdx
  unsigned int v9; // edx
  __int64 v10; // rax
  struct CHandleMap *v12; // r9
  unsigned __int16 v13; // dx
  struct CHandleMap *v14; // r9
  unsigned int v15; // [rsp+28h] [rbp-80h]
  struct IWbemServices *v16; // [rsp+30h] [rbp-78h]
  struct IWbemServices *v17; // [rsp+38h] [rbp-70h]
  struct IWbemObjectSink *v18; // [rsp+40h] [rbp-68h]
  struct IWbemContext *v19; // [rsp+48h] [rbp-60h]
  GUID Buf1; // [rsp+50h] [rbp-58h] BYREF
  GUID pclsid; // [rsp+60h] [rbp-48h] BYREF

  v4 = 1;
  if ( *((_DWORD *)this + 3) )
  {
    *(_DWORD *)this = 0;
    v5 = (CWMIStandardShell *)CWin32DefaultArena::WbemMemAlloc(0x18u);
    v6 = v5;
    *(_QWORD *)&pclsid.Data1 = v5;
    if ( v5 )
    {
      *(_QWORD *)v5 = 0;
      *((_QWORD *)v5 + 1) = 0;
      *((_DWORD *)v5 + 4) = 0;
    }
    else
    {
      v6 = 0;
    }
    if ( v6 )
    {
      Buf1 = a2->Guid;
      pclsid = 0;
      if ( CLSIDFromString(L"{B48D49A2-E777-11D0-A50C-00A0C9062910}", &pclsid) >= 0 && !memcmp_0(&Buf1, &pclsid, 0x10u) )
      {
        if ( !CWMIStandardShell::Initialize(
                v6,
                L"RuntimeBinaryMofsAdded",
                1,
                v12,
                *(_DWORD *)this,
                v15,
                v16,
                v17,
                v18,
                v19) )
          CWMIStandardShell::ProcessEvent(v6, v13, a2);
      }
      else
      {
        Buf1 = a2->Guid;
        pclsid = 0;
        if ( CLSIDFromString(L"{B48D49A3-E777-11d0-A50C-00A0C9062910}", &pclsid) >= 0
          && !memcmp_0(&Buf1, &pclsid, 0x10u) )
        {
          CWMIStandardShell::Initialize(
            v6,
            L"RuntimeBinaryMofsDeleted",
            1,
            v14,
            *(_DWORD *)this,
            v15,
            v16,
            v17,
            v18,
            v19);
        }
      }
      DebugTrace(10, "***************************************\n");
      v7 = *((_QWORD *)v6 + 1);
      if ( !v7 || (v8 = "BinaryMofEventChanged returned TRUE:\n", !*(_DWORD *)(v7 + 12)) )
        v8 = "BinaryMofEventChanged returned FALSE:\n";
      DebugTrace(10, v8);
      v10 = *((_QWORD *)v6 + 1);
      if ( !v10 || !*(_DWORD *)(v10 + 12) )
        v4 = 0;
      CWMIStandardShell::`scalar deleting destructor'(v6, v9);
    }
  }
  return v4;
}

```

## disassembly

```asm
0x1800066b4  push    rbx
0x1800066b6  push    rbp
0x1800066b7  push    rsi
0x1800066b8  push    rdi
0x1800066b9  sub     rsp, 88h
0x1800066c0  mov     rax, cs:__security_cookie
0x1800066c7  xor     rax, rsp
0x1800066ca  mov     [rsp+0A8h+var_38], rax
0x1800066cf  mov     rbp, rdx
0x1800066d2  mov     rsi, rcx
0x1800066d5  mov     edi, 1
0x1800066da  cmp     dword ptr [rcx+0Ch], 0
0x1800066de  jz      loc_1800067C2
0x1800066e4  mov     dword ptr [rcx], 0
0x1800066ea  lea     ecx, [rdi+17h]
0x1800066ed  call    cs:__imp_?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z; CWin32DefaultArena::WbemMemAlloc(unsigned __int64)
0x1800066f3  mov     rbx, rax
0x1800066f6  mov     qword ptr [rsp+0A8h+pclsid.Data1], rax
0x1800066fb  test    rax, rax
0x1800066fe  jz      loc_1800067DD
0x180006704  mov     qword ptr [rax], 0
0x18000670b  mov     qword ptr [rax+8], 0
0x180006713  mov     dword ptr [rax+10h], 0
0x18000671a  test    rbx, rbx
0x18000671d  jz      loc_1800067C2
0x180006723  movups  xmm0, xmmword ptr [rbp+18h]
0x180006727  movdqu  [rsp+0A8h+Buf1], xmm0
0x18000672d  xorps   xmm1, xmm1
0x180006730  movups  xmmword ptr [rsp+0A8h+pclsid.Data1], xmm1
0x180006735  lea     rdx, [rsp+0A8h+pclsid]; pclsid
0x18000673a  lea     rcx, sz; "{B48D49A2-E777-11D0-A50C-00A0C9062910}"
0x180006741  call    cs:__imp_CLSIDFromString
0x180006747  test    eax, eax
0x180006749  jns     loc_1800067E4
0x18000674f  movups  xmm0, xmmword ptr [rbp+18h]
0x180006753  movdqu  [rsp+0A8h+Buf1], xmm0
0x180006759  xorps   xmm1, xmm1
0x18000675c  movups  xmmword ptr [rsp+0A8h+pclsid.Data1], xmm1
0x180006761  lea     rdx, [rsp+0A8h+pclsid]; pclsid
0x180006766  lea     rcx, aB48d49a3E77711; "{B48D49A3-E777-11d0-A50C-00A0C9062910}"
0x18000676d  call    cs:__imp_CLSIDFromString
0x180006773  test    eax, eax
0x180006775  jns     loc_180006831
0x18000677b  lea     rdx, asc_180023540; "***************************************"...
0x180006782  mov     esi, 0Ah
0x180006787  mov     ecx, esi
0x180006789  call    cs:__imp_?DebugTrace@@YAHDPEBDZZ; DebugTrace(char,char const *,...)
0x18000678f  mov     rax, [rbx+8]
0x180006793  test    rax, rax
0x180006796  jnz     loc_18000686B
0x18000679c  lea     rdx, aBinarymofevent; "BinaryMofEventChanged returned FALSE:\n"
0x1800067a3  mov     ecx, esi
0x1800067a5  call    cs:__imp_?DebugTrace@@YAHDPEBDZZ; DebugTrace(char,char const *,...)
0x1800067ab  mov     rax, [rbx+8]
0x1800067af  test    rax, rax
0x1800067b2  jnz     loc_180006881
0x1800067b8  xor     edi, edi
0x1800067ba  mov     rcx, rbx; this
0x1800067bd  call    ??_GCWMIStandardShell@@QEAAPEAXI@Z; CWMIStandardShell::`scalar deleting destructor'(uint)
0x1800067c2  mov     eax, edi
0x1800067c4  mov     rcx, [rsp+0A8h+var_38]
0x1800067c9  xor     rcx, rsp; StackCookie
0x1800067cc  call    __security_check_cookie
0x1800067d1  add     rsp, 88h
0x1800067d8  pop     rdi
0x1800067d9  pop     rsi
0x1800067da  pop     rbp
0x1800067db  pop     rbx
0x1800067dc  retn
0x1800067dd  xor     ebx, ebx
0x1800067df  jmp     loc_18000671A
0x1800067e4  mov     r8d, 10h; Size
0x1800067ea  lea     rdx, [rsp+0A8h+pclsid]; Buf2
0x1800067ef  lea     rcx, [rsp+0A8h+Buf1]; Buf1
0x1800067f4  call    memcmp_0
0x1800067f9  test    eax, eax
0x1800067fb  jnz     loc_18000674F
0x180006801  mov     eax, [rsi]
0x180006803  mov     [rsp+0A8h+var_88], eax; int
0x180006807  mov     r8d, edi; int
0x18000680a  lea     rdx, aRuntimebinarym_0; "RuntimeBinaryMofsAdded"
0x180006811  mov     rcx, rbx; this
0x180006814  call    ?Initialize@CWMIStandardShell@@QEAAJPEAGHPEAVCHandleMap@@HKPEAUIWbemServices@@2PEAUIWbemObjectSink@@PEAUIWbemContext@@@Z; CWMIStandardShell::Initialize(ushort *,int,CHandleMap *,int,ulong,IWbemServices *,IWbemServices *,IWbemObjectSink *,IWbemContext *)
0x180006819  test    eax, eax
0x18000681b  jnz     loc_18000677B
0x180006821  mov     r8, rbp; struct _WNODE_HEADER *
0x180006824  mov     rcx, rbx; this
0x180006827  call    ?ProcessEvent@CWMIStandardShell@@QEAAJGPEAU_WNODE_HEADER@@@Z; CWMIStandardShell::ProcessEvent(ushort,_WNODE_HEADER *)
0x18000682c  jmp     loc_18000677B
0x180006831  mov     r8d, 10h; Size
0x180006837  lea     rdx, [rsp+0A8h+pclsid]; Buf2
0x18000683c  lea     rcx, [rsp+0A8h+Buf1]; Buf1
0x180006841  call    memcmp_0
0x180006846  test    eax, eax
0x180006848  jnz     loc_18000677B
0x18000684e  mov     eax, [rsi]
0x180006850  mov     [rsp+0A8h+var_88], eax; int
0x180006854  mov     r8d, edi; int
0x180006857  lea     rdx, aRuntimebinarym; "RuntimeBinaryMofsDeleted"
0x18000685e  mov     rcx, rbx; this
0x180006861  call    ?Initialize@CWMIStandardShell@@QEAAJPEAGHPEAVCHandleMap@@HKPEAUIWbemServices@@2PEAUIWbemObjectSink@@PEAUIWbemContext@@@Z; CWMIStandardShell::Initialize(ushort *,int,CHandleMap *,int,ulong,IWbemServices *,IWbemServices *,IWbemObjectSink *,IWbemContext *)
0x180006866  jmp     loc_18000677B
0x18000686b  cmp     dword ptr [rax+0Ch], 0
0x18000686f  lea     rdx, aBinarymofevent_0; "BinaryMofEventChanged returned TRUE:\n"
0x180006876  jnz     loc_1800067A3
0x18000687c  jmp     loc_18000679C
0x180006881  cmp     dword ptr [rax+0Ch], 0
0x180006885  jnz     loc_1800067BA
0x18000688b  jmp     loc_1800067B8
```
