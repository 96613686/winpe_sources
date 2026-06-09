# ABO_WRAPPER::InitializeTreeAndState(void)

- ea: `0x18000e99c`
- end: `0x18000eb50`
- name: `?InitializeTreeAndState@ABO_WRAPPER@@QEAAJXZ`
- size: `436`
- prototype: `__int64 __fastcall(ABO_WRAPPER *__hidden this)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x18000dde0`

## callees

- `0x180001f90`
- `0x180002990`
- `0x180003f14`
- `0x180004284`
- `0x180004f98`
- `0x18000ae70`
- `0x18000e99c`
- `0x18002c010`

## import_xrefs

- `nativerd!CreateNativeConfigurationSystem` at `0x18000e9bd`
- `nativerd!CreateNativeConfigurationSystem` at `0x18000e9bd`

## string_xrefs

- `0x18000e9cb`: `Failed to create native config system.  hr = %08x\n`
- `0x18000eabe`: `Could create NotifyItem due to Error = %X`
- `0x18000ea9f`: `Failed to add change listener to config system.  hr = %08x\n`

## pseudocode

```c
__int64 __fastcall ABO_WRAPPER::InitializeTreeAndState(ABO_WRAPPER *this)
{
  int Tree; // eax
  int v3; // edi
  struct ABO_TREE *v4; // rbx
  const unsigned __int16 *v5; // rdx
  ABO_TREE *v6; // rax
  ABO_TREE *v7; // rax
  _QWORD *v8; // rax
  struct INativeConfigurationSystem *v9; // rax
  struct INativeConfigurationSystem *v11; // [rsp+58h] [rbp+10h] BYREF

  v11 = 0;
  Tree = CreateNativeConfigurationSystem(L"MACHINE/WEBROOT/APPHOST", &v11);
  v3 = Tree;
  if ( Tree >= 0 )
  {
    v6 = (ABO_TREE *)operator new(0x50u);
    if ( v6 )
    {
      v7 = ABO_TREE::ABO_TREE(v6, v11);
      v4 = v7;
      if ( v7 )
      {
        Tree = ABO_TREE::GenerateTree(v7);
        v3 = Tree;
        if ( Tree >= 0 )
        {
          if ( !*((_QWORD *)this + 30) )
          {
            v8 = operator new(0x18u);
            if ( !v8 )
            {
              v3 = -2147024888;
              *((_QWORD *)this + 30) = 0;
              ABO_MAPPER_LOG::WriteLogEntry(
                (HANDLE *)g_pAboLog,
                L"Could create NotifyItem due to Error = %X",
                2147942408LL);
              goto LABEL_20;
            }
            *(_DWORD *)v8 = 0;
            v8[1] = 0;
            *((_DWORD *)v8 + 4) = 1;
            *((_QWORD *)this + 30) = v8;
          }
          v3 = (*(__int64 (__fastcall **)(struct INativeConfigurationSystem *, unsigned __int64))(*(_QWORD *)v11 + 40LL))(
                 v11,
                 ((unsigned __int64)this + 8) & -(__int64)(this != 0));
          if ( v3 < 0 )
          {
            (*(void (__fastcall **)(struct INativeConfigurationSystem *, unsigned __int64))(*(_QWORD *)v11 + 48LL))(
              v11,
              ((unsigned __int64)this + 8) & -(__int64)(this != 0));
            ABO_MAPPER_LOG::WriteLogEntry(
              (HANDLE *)g_pAboLog,
              L"Failed to add change listener to config system.  hr = %08x\n",
              (unsigned int)v3);
            goto LABEL_20;
          }
          Tree = NOTIFY_ITEM::GenerateChangeList(*((NOTIFY_ITEM **)this + 30), v4);
          v3 = Tree;
          if ( Tree >= 0 )
          {
            _InterlockedIncrement((volatile signed __int32 *)this + 32);
            v9 = v11;
            *((_QWORD *)this + 3) = v4;
            v4 = 0;
            v11 = 0;
            *((_QWORD *)this + 15) = v9;
            *((_DWORD *)this + 58) = 1;
            goto LABEL_20;
          }
          v5 = L"Could not generate change list due to Error = %X";
        }
        else
        {
          v5 = L"GenerateTree() failed with %08x\n";
        }
        goto LABEL_3;
      }
    }
    else
    {
      v4 = 0;
    }
    v3 = -2147024888;
    goto LABEL_20;
  }
  v4 = 0;
  v5 = L"Failed to create native config system.  hr = %08x\n";
LABEL_3:
  ABO_MAPPER_LOG::WriteLogEntry((HANDLE *)g_pAboLog, v5, (unsigned int)Tree);
LABEL_20:
  if ( v11 )
  {
    (*(void (__fastcall **)(struct INativeConfigurationSystem *))(*(_QWORD *)v11 + 16LL))(v11);
    v11 = 0;
  }
  if ( v4 )
    HANDLE_ENTRY::DereferenceHandleEntry(v4);
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x18000e99c  push    rbx
0x18000e99e  push    rbp
0x18000e99f  push    rsi
0x18000e9a0  push    rdi
0x18000e9a1  sub     rsp, 28h
0x18000e9a5  mov     rsi, rcx
0x18000e9a8  mov     [rsp+48h+arg_8], 0
0x18000e9b1  lea     rcx, aMachineWebroot; "MACHINE/WEBROOT/APPHOST"
0x18000e9b8  lea     rdx, [rsp+48h+arg_8]
0x18000e9bd  call    cs:__imp_?CreateNativeConfigurationSystem@@YAJPEBGPEAPEAVINativeConfigurationSystem@@@Z; CreateNativeConfigurationSystem(ushort const *,INativeConfigurationSystem * *)
0x18000e9c3  mov     edi, eax
0x18000e9c5  test    eax, eax
0x18000e9c7  jns     short loc_18000E9E6
0x18000e9c9  xor     ebx, ebx
0x18000e9cb  lea     rdx, aFailedToCreate; "Failed to create native config system. "...
0x18000e9d2  mov     r8d, eax
0x18000e9d5  mov     rcx, cs:?g_pAboLog@@3PEAVABO_MAPPER_LOG@@EA; this
0x18000e9dc  call    ?WriteLogEntry@ABO_MAPPER_LOG@@QEAAJPEBGZZ; ABO_MAPPER_LOG::WriteLogEntry(ushort const *,...)
0x18000e9e1  jmp     loc_18000EB19
0x18000e9e6  mov     ecx, 50h ; 'P'; Size
0x18000e9eb  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000e9f0  test    rax, rax
0x18000e9f3  jz      loc_18000EB12
0x18000e9f9  mov     rdx, [rsp+48h+arg_8]; struct INativeConfigurationSystem *
0x18000e9fe  mov     rcx, rax; this
0x18000ea01  call    ??0ABO_TREE@@QEAA@PEAVINativeConfigurationSystem@@@Z; ABO_TREE::ABO_TREE(INativeConfigurationSystem *)
0x18000ea06  mov     rbx, rax
0x18000ea09  test    rax, rax
0x18000ea0c  jz      loc_18000EB14
0x18000ea12  mov     rcx, rax; this
0x18000ea15  call    ?GenerateTree@ABO_TREE@@QEAAJXZ; ABO_TREE::GenerateTree(void)
0x18000ea1a  mov     edi, eax
0x18000ea1c  test    eax, eax
0x18000ea1e  jns     short loc_18000EA29
0x18000ea20  lea     rdx, aGeneratetreeFa; "GenerateTree() failed with %08x\n"
0x18000ea27  jmp     short loc_18000E9D2
0x18000ea29  cmp     qword ptr [rsi+0F0h], 0
0x18000ea31  jnz     short loc_18000EA5E
0x18000ea33  mov     ecx, 18h; Size
0x18000ea38  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000ea3d  test    rax, rax
0x18000ea40  jz      short loc_18000EAAB
0x18000ea42  mov     dword ptr [rax], 0
0x18000ea48  mov     qword ptr [rax+8], 0
0x18000ea50  mov     dword ptr [rax+10h], 1
0x18000ea57  mov     [rsi+0F0h], rax
0x18000ea5e  lea     rcx, [rsi+8]
0x18000ea62  mov     rax, rsi
0x18000ea65  neg     rax
0x18000ea68  sbb     rbp, rbp
0x18000ea6b  and     rbp, rcx
0x18000ea6e  mov     rcx, [rsp+48h+arg_8]
0x18000ea73  mov     rdx, rbp
0x18000ea76  mov     rax, [rcx]
0x18000ea79  mov     rax, [rax+28h]
0x18000ea7d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ea82  mov     edi, eax
0x18000ea84  test    eax, eax
0x18000ea86  jns     short loc_18000EACA
0x18000ea88  mov     rcx, [rsp+48h+arg_8]
0x18000ea8d  mov     rdx, rbp
0x18000ea90  mov     rax, [rcx]
0x18000ea93  mov     rax, [rax+30h]
0x18000ea97  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ea9c  mov     r8d, edi
0x18000ea9f  lea     rdx, aFailedToAddCha; "Failed to add change listener to config"...
0x18000eaa6  jmp     loc_18000E9D5
0x18000eaab  mov     edi, 80070008h
0x18000eab0  mov     qword ptr [rsi+0F0h], 0
0x18000eabb  mov     r8d, edi
0x18000eabe  lea     rdx, aCouldCreateNot; "Could create NotifyItem due to Error = "...
0x18000eac5  jmp     loc_18000E9D5
0x18000eaca  mov     rcx, [rsi+0F0h]; this
0x18000ead1  mov     rdx, rbx; struct ABO_TREE *
0x18000ead4  call    ?GenerateChangeList@NOTIFY_ITEM@@QEAAJPEAVABO_TREE@@@Z; NOTIFY_ITEM::GenerateChangeList(ABO_TREE *)
0x18000ead9  mov     edi, eax
0x18000eadb  test    eax, eax
0x18000eadd  jns     short loc_18000EAEB
0x18000eadf  lea     rdx, aCouldNotGenera; "Could not generate change list due to E"...
0x18000eae6  jmp     loc_18000E9D2
0x18000eaeb  lock inc dword ptr [rsi+80h]
0x18000eaf2  mov     rax, [rsp+48h+arg_8]
0x18000eaf7  mov     [rsi+18h], rbx
0x18000eafb  xor     ebx, ebx
0x18000eafd  mov     [rsp+48h+arg_8], rbx
0x18000eb02  mov     [rsi+78h], rax
0x18000eb06  mov     dword ptr [rsi+0E8h], 1
0x18000eb10  jmp     short loc_18000EB19
0x18000eb12  xor     ebx, ebx
0x18000eb14  mov     edi, 80070008h
0x18000eb19  mov     rcx, [rsp+48h+arg_8]
0x18000eb1e  test    rcx, rcx
0x18000eb21  jz      short loc_18000EB38
0x18000eb23  mov     rax, [rcx]
0x18000eb26  mov     rax, [rax+10h]
0x18000eb2a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000eb2f  mov     [rsp+48h+arg_8], 0
0x18000eb38  test    rbx, rbx
0x18000eb3b  jz      short loc_18000EB45
0x18000eb3d  mov     rcx, rbx; this
0x18000eb40  call    ?DereferenceHandleEntry@HANDLE_ENTRY@@QEAAXXZ; HANDLE_ENTRY::DereferenceHandleEntry(void)
0x18000eb45  mov     eax, edi
0x18000eb47  add     rsp, 28h
0x18000eb4b  pop     rdi
0x18000eb4c  pop     rsi
0x18000eb4d  pop     rbp
0x18000eb4e  pop     rbx
0x18000eb4f  retn
```
