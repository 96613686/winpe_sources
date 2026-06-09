# ABO_TREE::GenerateTree(void)

- ea: `0x180004f98`
- end: `0x1800051a6`
- name: `?GenerateTree@ABO_TREE@@QEAAJXZ`
- size: `526`
- prototype: `__int64 __fastcall(ABO_TREE *__hidden this)`
- caller_count: `1`
- callee_count: `14`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x18000e99c`

## callees

- `0x180001f90`
- `0x18000473c`
- `0x180004828`
- `0x180004b80`
- `0x180004f98`
- `0x1800051ac`
- `0x18000526c`
- `0x180006484`
- `0x180006b78`
- `0x180007080`
- `0x180008050`
- `0x18000aa08`
- `0x180027294`
- `0x18002c010`

## import_xrefs

- `iisutil!?Alloc@ALLOC_CACHE_HANDLER@@QEAAPEAXXZ` at `0x180005072`
- `iisutil!?Alloc@ALLOC_CACHE_HANDLER@@QEAAPEAXXZ` at `0x1800050a4`
- `iisutil!?Alloc@ALLOC_CACHE_HANDLER@@QEAAPEAXXZ` at `0x180005072`
- `iisutil!?Alloc@ALLOC_CACHE_HANDLER@@QEAAPEAXXZ` at `0x1800050a4`

## string_xrefs

- `0x180004ff7`: `GetConfigFile() failed with %08x\n`
- `0x18000503a`: `Could not check File Path Info. Error = %X`
- `0x180005062`: `Could not get Config File time. Error = %X`
- `0x1800050e6`: `IIsComputer`

## pseudocode

```c
__int64 __fastcall ABO_TREE::GenerateTree(ABO_TREE *this)
{
  __int64 v2; // rcx
  ABO_NODE *v3; // rdi
  struct INativeConfigFile **v4; // r14
  int v5; // eax
  ABO_MAPPER_LOG *v6; // rcx
  int ConfigFileSecurityDescriptor; // ebx
  int ConfigFilePathInfo; // eax
  int v9; // eax
  ABO_NODE *v10; // rax
  ABO_NODE *v11; // rax
  ABO_NODE *v12; // rax
  int RootNode; // eax
  int LocationNodesAndProperties; // eax
  int CustomNodesAndProperties; // eax
  struct INativeSectionException *v17; // [rsp+60h] [rbp+8h] BYREF

  v2 = *((_QWORD *)this + 3);
  v3 = 0;
  v17 = 0;
  v4 = (struct INativeConfigFile **)((char *)this + 32);
  v5 = (*(__int64 (__fastcall **)(__int64, const unsigned __int16 *, char *, struct INativeSectionException **))(*(_QWORD *)v2 + 88LL))(
         v2,
         L"MACHINE/WEBROOT/APPHOST",
         (char *)this + 32,
         &v17);
  ConfigFileSecurityDescriptor = v5;
  if ( v5 >= 0 )
  {
    ConfigFileSecurityDescriptor = ABO_TREE::GetConfigFileSecurityDescriptor(this);
    if ( ConfigFileSecurityDescriptor >= 0 )
    {
      ConfigFilePathInfo = ABO_TREE::GetConfigFilePathInfo(this, *v4);
      if ( ConfigFilePathInfo < 0 )
        ABO_MAPPER_LOG::WriteLogEntry(
          g_pAboLog,
          L"Could not check File Path Info. Error = %X",
          (unsigned int)ConfigFilePathInfo);
      v9 = (*(__int64 (__fastcall **)(struct INativeConfigFile *, char *))(*(_QWORD *)*v4 + 72LL))(
             *v4,
             (char *)this + 68);
      ConfigFileSecurityDescriptor = v9;
      if ( v9 >= 0 )
      {
        v10 = (ABO_NODE *)ALLOC_CACHE_HANDLER::Alloc((ALLOC_CACHE_HANDLER *)ABO_NODE::sm_pachAboNodes);
        if ( v10 )
          v10 = ABO_NODE::ABO_NODE(v10, this, 1);
        *((_QWORD *)this + 2) = v10;
        if ( v10
          && (v11 = (ABO_NODE *)ALLOC_CACHE_HANDLER::Alloc((ALLOC_CACHE_HANDLER *)ABO_NODE::sm_pachAboNodes)) != 0
          && (v12 = ABO_NODE::ABO_NODE(v11, this, 1), (v3 = v12) != 0) )
        {
          ConfigFileSecurityDescriptor = ABO_NODE::Create(v12, L"LM");
          if ( ConfigFileSecurityDescriptor >= 0 )
          {
            ConfigFileSecurityDescriptor = ABO_NODE::SetKeyType(v3, L"IIsComputer");
            if ( ConfigFileSecurityDescriptor >= 0 )
            {
              ConfigFileSecurityDescriptor = ABO_NODE::AddChildNode(*((ABO_NODE **)this + 2), v3);
              if ( ConfigFileSecurityDescriptor >= 0 )
              {
                RootNode = ABO_NODE::GenerateRootNode((struct ABO_TREE **)v3);
                ConfigFileSecurityDescriptor = RootNode;
                if ( RootNode >= 0 )
                {
                  LocationNodesAndProperties = ABO_TREE::GenerateLocationNodesAndProperties(this);
                  ConfigFileSecurityDescriptor = LocationNodesAndProperties;
                  if ( LocationNodesAndProperties >= 0 )
                  {
                    CustomNodesAndProperties = ABO_TREE::GenerateCustomNodesAndProperties(this);
                    ConfigFileSecurityDescriptor = CustomNodesAndProperties;
                    if ( CustomNodesAndProperties < 0 )
                    {
                      ABO_MAPPER_LOG::WriteLogEntry(
                        g_pAboLog,
                        L"Failed to generate custom nodes.  error = %08x\n",
                        (unsigned int)CustomNodesAndProperties);
                      ConfigFileSecurityDescriptor = 0;
                    }
                  }
                  else
                  {
                    ABO_MAPPER_LOG::WriteLogEntry(
                      g_pAboLog,
                      L"Failed to generate location nodes.  error = %08x\n",
                      (unsigned int)LocationNodesAndProperties);
                  }
                }
                else
                {
                  ABO_MAPPER_LOG::WriteLogEntry(
                    g_pAboLog,
                    L"Failed to generate root node.  error = %08x\n",
                    (unsigned int)RootNode);
                }
              }
            }
          }
        }
        else
        {
          ConfigFileSecurityDescriptor = -2147024888;
        }
      }
      else
      {
        ABO_MAPPER_LOG::WriteLogEntry(g_pAboLog, L"Could not get Config File time. Error = %X", (unsigned int)v9);
      }
    }
  }
  else if ( v17 )
  {
    ABO_MAPPER_LOG::WriteConfigSectionException(v6, L"<unspecified-section>", L"MACHINE/WEBROOT/APPHOST", v17);
  }
  else
  {
    ABO_MAPPER_LOG::WriteLogEntry(g_pAboLog, L"GetConfigFile() failed with %08x\n", (unsigned int)v5);
  }
  if ( v17 )
  {
    (*(void (__fastcall **)(struct INativeSectionException *))(*(_QWORD *)v17 + 16LL))(v17);
    v17 = 0;
  }
  if ( v3 )
    ABO_NODE::DereferenceAboNode(v3);
  return (unsigned int)ConfigFileSecurityDescriptor;
}

```

## disassembly

```asm
0x180004f98  push    rbx
0x180004f9a  push    rsi
0x180004f9b  push    rdi
0x180004f9c  push    r14
0x180004f9e  sub     rsp, 38h
0x180004fa2  mov     rsi, rcx
0x180004fa5  lea     r9, [rsp+58h+arg_0]
0x180004faa  mov     rcx, [rcx+18h]
0x180004fae  lea     rdx, aMachineWebroot; "MACHINE/WEBROOT/APPHOST"
0x180004fb5  xor     edi, edi
0x180004fb7  mov     [rsp+58h+arg_0], rdi
0x180004fbc  lea     r14, [rsi+20h]
0x180004fc0  mov     rax, [rcx]
0x180004fc3  mov     r8, r14
0x180004fc6  mov     rax, [rax+58h]
0x180004fca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004fcf  mov     ebx, eax
0x180004fd1  test    eax, eax
0x180004fd3  jns     short loc_180005012
0x180004fd5  mov     r9, [rsp+58h+arg_0]; struct INativeSectionException *
0x180004fda  test    r9, r9
0x180004fdd  jz      short loc_180004FF7
0x180004fdf  lea     r8, aMachineWebroot; "MACHINE/WEBROOT/APPHOST"
0x180004fe6  lea     rdx, aUnspecifiedSec; "<unspecified-section>"
0x180004fed  call    ?WriteConfigSectionException@ABO_MAPPER_LOG@@QEAAJPEBG0PEAVINativeSectionException@@@Z; ABO_MAPPER_LOG::WriteConfigSectionException(ushort const *,ushort const *,INativeSectionException *)
0x180004ff2  jmp     loc_18000516E
0x180004ff7  lea     rdx, aGetconfigfileF; "GetConfigFile() failed with %08x\n"
0x180004ffe  mov     rcx, cs:?g_pAboLog@@3PEAVABO_MAPPER_LOG@@EA; this
0x180005005  mov     r8d, eax
0x180005008  call    ?WriteLogEntry@ABO_MAPPER_LOG@@QEAAJPEBGZZ; ABO_MAPPER_LOG::WriteLogEntry(ushort const *,...)
0x18000500d  jmp     loc_18000516E
0x180005012  mov     rcx, rsi; this
0x180005015  call    ?GetConfigFileSecurityDescriptor@ABO_TREE@@AEAAJXZ; ABO_TREE::GetConfigFileSecurityDescriptor(void)
0x18000501a  mov     ebx, eax
0x18000501c  test    eax, eax
0x18000501e  js      loc_18000516E
0x180005024  mov     rdx, [r14]; struct INativeConfigFile *
0x180005027  mov     rcx, rsi; this
0x18000502a  call    ?GetConfigFilePathInfo@ABO_TREE@@AEAAJPEAVINativeConfigFile@@@Z; ABO_TREE::GetConfigFilePathInfo(INativeConfigFile *)
0x18000502f  test    eax, eax
0x180005031  jns     short loc_180005049
0x180005033  mov     rcx, cs:?g_pAboLog@@3PEAVABO_MAPPER_LOG@@EA; this
0x18000503a  lea     rdx, aCouldNotCheckF; "Could not check File Path Info. Error ="...
0x180005041  mov     r8d, eax
0x180005044  call    ?WriteLogEntry@ABO_MAPPER_LOG@@QEAAJPEBGZZ; ABO_MAPPER_LOG::WriteLogEntry(ushort const *,...)
0x180005049  mov     rcx, [r14]
0x18000504c  lea     rdx, [rsi+44h]
0x180005050  mov     rax, [rcx]
0x180005053  mov     rax, [rax+48h]
0x180005057  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000505c  mov     ebx, eax
0x18000505e  test    eax, eax
0x180005060  jns     short loc_18000506B
0x180005062  lea     rdx, aCouldNotGetCon; "Could not get Config File time. Error ="...
0x180005069  jmp     short loc_180004FFE
0x18000506b  mov     rcx, cs:?sm_pachAboNodes@ABO_NODE@@0PEAVALLOC_CACHE_HANDLER@@EA; ALLOC_CACHE_HANDLER * ABO_NODE::sm_pachAboNodes
0x180005072  call    cs:__imp_?Alloc@ALLOC_CACHE_HANDLER@@QEAAPEAXXZ; ALLOC_CACHE_HANDLER::Alloc(void)
0x180005078  mov     ebx, 1
0x18000507d  test    rax, rax
0x180005080  jz      short loc_180005090
0x180005082  mov     r8d, ebx; int
0x180005085  mov     rdx, rsi; struct ABO_TREE *
0x180005088  mov     rcx, rax; this
0x18000508b  call    ??0ABO_NODE@@QEAA@PEAVABO_TREE@@H@Z; ABO_NODE::ABO_NODE(ABO_TREE *,int)
0x180005090  mov     [rsi+10h], rax
0x180005094  test    rax, rax
0x180005097  jz      loc_180005169
0x18000509d  mov     rcx, cs:?sm_pachAboNodes@ABO_NODE@@0PEAVALLOC_CACHE_HANDLER@@EA; ALLOC_CACHE_HANDLER * ABO_NODE::sm_pachAboNodes
0x1800050a4  call    cs:__imp_?Alloc@ALLOC_CACHE_HANDLER@@QEAAPEAXXZ; ALLOC_CACHE_HANDLER::Alloc(void)
0x1800050aa  test    rax, rax
0x1800050ad  jz      loc_180005169
0x1800050b3  mov     r8d, ebx; int
0x1800050b6  mov     rdx, rsi; struct ABO_TREE *
0x1800050b9  mov     rcx, rax; this
0x1800050bc  call    ??0ABO_NODE@@QEAA@PEAVABO_TREE@@H@Z; ABO_NODE::ABO_NODE(ABO_TREE *,int)
0x1800050c1  mov     rdi, rax
0x1800050c4  test    rax, rax
0x1800050c7  jz      loc_180005169
0x1800050cd  lea     rdx, aLm; "LM"
0x1800050d4  mov     rcx, rax; this
0x1800050d7  call    ?Create@ABO_NODE@@QEAAJPEBG@Z; ABO_NODE::Create(ushort const *)
0x1800050dc  mov     ebx, eax
0x1800050de  test    eax, eax
0x1800050e0  js      loc_18000516E
0x1800050e6  lea     rdx, aIiscomputer; "IIsComputer"
0x1800050ed  mov     rcx, rdi; this
0x1800050f0  call    ?SetKeyType@ABO_NODE@@QEAAJPEBG@Z; ABO_NODE::SetKeyType(ushort const *)
0x1800050f5  mov     ebx, eax
0x1800050f7  test    eax, eax
0x1800050f9  js      short loc_18000516E
0x1800050fb  mov     rcx, [rsi+10h]; this
0x1800050ff  mov     rdx, rdi; struct ABO_NODE *
0x180005102  call    ?AddChildNode@ABO_NODE@@QEAAJPEAV1@@Z; ABO_NODE::AddChildNode(ABO_NODE *)
0x180005107  mov     ebx, eax
0x180005109  test    eax, eax
0x18000510b  js      short loc_18000516E
0x18000510d  mov     rcx, rdi; this
0x180005110  call    ?GenerateRootNode@ABO_NODE@@QEAAJXZ; ABO_NODE::GenerateRootNode(void)
0x180005115  mov     ebx, eax
0x180005117  test    eax, eax
0x180005119  jns     short loc_180005127
0x18000511b  lea     rdx, aFailedToGenera_15; "Failed to generate root node.  error = "...
0x180005122  jmp     loc_180004FFE
0x180005127  mov     rcx, rsi; this
0x18000512a  call    ?GenerateLocationNodesAndProperties@ABO_TREE@@AEAAJXZ; ABO_TREE::GenerateLocationNodesAndProperties(void)
0x18000512f  mov     ebx, eax
0x180005131  test    eax, eax
0x180005133  jns     short loc_180005141
0x180005135  lea     rdx, aFailedToGenera_13; "Failed to generate location nodes.  err"...
0x18000513c  jmp     loc_180004FFE
0x180005141  mov     rcx, rsi; this
0x180005144  call    ?GenerateCustomNodesAndProperties@ABO_TREE@@AEAAJXZ; ABO_TREE::GenerateCustomNodesAndProperties(void)
0x180005149  mov     ebx, eax
0x18000514b  test    eax, eax
0x18000514d  jns     short loc_18000516E
0x18000514f  mov     rcx, cs:?g_pAboLog@@3PEAVABO_MAPPER_LOG@@EA; this
0x180005156  lea     rdx, aFailedToGenera_25; "Failed to generate custom nodes.  error"...
0x18000515d  mov     r8d, eax
0x180005160  call    ?WriteLogEntry@ABO_MAPPER_LOG@@QEAAJPEBGZZ; ABO_MAPPER_LOG::WriteLogEntry(ushort const *,...)
0x180005165  xor     ebx, ebx
0x180005167  jmp     short loc_18000516E
0x180005169  mov     ebx, 80070008h
0x18000516e  mov     rcx, [rsp+58h+arg_0]
0x180005173  test    rcx, rcx
0x180005176  jz      short loc_18000518D
0x180005178  mov     rax, [rcx]
0x18000517b  mov     rax, [rax+10h]
0x18000517f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005184  mov     [rsp+58h+arg_0], 0
0x18000518d  test    rdi, rdi
0x180005190  jz      short loc_18000519A
0x180005192  mov     rcx, rdi; this
0x180005195  call    ?DereferenceAboNode@ABO_NODE@@QEAAXXZ; ABO_NODE::DereferenceAboNode(void)
0x18000519a  mov     eax, ebx
0x18000519c  add     rsp, 38h
0x1800051a0  pop     r14
0x1800051a2  pop     rdi
0x1800051a3  pop     rsi
0x1800051a4  pop     rbx
0x1800051a5  retn
```
