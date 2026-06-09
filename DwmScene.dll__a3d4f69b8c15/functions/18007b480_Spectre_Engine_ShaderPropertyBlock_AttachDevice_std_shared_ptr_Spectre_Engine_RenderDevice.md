# Spectre::Engine::ShaderPropertyBlock::AttachDevice(std::shared_ptr<Spectre::Engine::RenderDevice>)

- ea: `0x18007b480`
- end: `0x18007b696`
- name: `?AttachDevice@ShaderPropertyBlock@Engine@Spectre@@UEAAXV?$shared_ptr@VRenderDevice@Engine@Spectre@@@std@@@Z`
- size: `534`
- prototype: ``
- caller_count: `3`
- callee_count: `15`
- tags: `broker_com_uri`

## callers

- `0x1800416f0`
- `0x180048040`
- `0x18007b13c`

## callees

- `0x18000ca90`
- `0x18000dfa2`
- `0x18001128c`
- `0x180011f64`
- `0x180012d98`
- `0x1800285a0`
- `0x18002921c`
- `0x180038ddc`
- `0x18007a690`
- `0x18007a75c`
- `0x18007aab0`
- `0x18007b480`
- `0x18007b69c`
- `0x18007b814`
- `0x1800e7010`

## string_xrefs

- `0x18007b5e0`: `ShaderPropertyBlock::AttachDevice() -- failed to create constant buffer`
- `0x18007b5f1`: `onecoreuap\windows\dwm\spectre\engine\products\components\nativerenderer\cpp\source\engine\shaderpropertyblock.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
void __fastcall Spectre::Engine::ShaderPropertyBlock::AttachDevice(_QWORD *a1, _QWORD *a2)
{
  std::_Ref_count_base *v4; // rcx
  __int64 v5; // rax
  std::_Ref_count_base *v6; // rdx
  std::_Ref_count_base *v7; // rcx
  unsigned int v8; // r15d
  __int64 v9; // rdi
  __int64 v10; // rbx
  __int64 v11; // rax
  int v12; // eax
  int v13; // r8d
  __int64 v14; // [rsp+38h] [rbp-71h] BYREF
  std::_Ref_count_base *v15; // [rsp+40h] [rbp-69h]
  __int64 v16; // [rsp+48h] [rbp-61h] BYREF
  std::_Ref_count_base *v17; // [rsp+50h] [rbp-59h]
  _QWORD *v18; // [rsp+58h] [rbp-51h]
  _BYTE v19[32]; // [rsp+60h] [rbp-49h] BYREF
  _BYTE v20[32]; // [rsp+80h] [rbp-29h] BYREF
  _BYTE pExceptionObject[56]; // [rsp+A0h] [rbp-9h] BYREF

  v18 = a2;
  if ( !*(_DWORD *)(*a2 + 244LL) || a1[4] == a1[5] )
  {
    v4 = (std::_Ref_count_base *)a2[1];
  }
  else
  {
    Spectre::Engine::Lockable::VerifyWriteAccess((Spectre::Engine::Lockable *)(*a2 + 24LL));
    if ( !a1[16] )
    {
      Spectre::Engine::Engine::CreateResource<Spectre::Engine::ConstantBuffer,>(*(_QWORD *)(*a2 + 3984LL), &v14);
      v5 = v14;
      v6 = v15;
      v14 = 0;
      v15 = 0;
      a1[16] = v5;
      v7 = (std::_Ref_count_base *)a1[17];
      a1[17] = v6;
      if ( v7 )
      {
        std::_Ref_count_base::_Decref(v7);
        if ( v15 )
          std::_Ref_count_base::_Decref(v15);
      }
    }
    v8 = *(_DWORD *)(*a2 + 244LL);
    if ( !(unsigned __int8)Spectre::Engine::ConstantBuffer::Contains(a1[16], v8) )
    {
      v9 = *a2;
      Spectre::Engine::ResourceFactory::CreateResource<Spectre::Engine::DeviceConstantBuffer>(*a2 + 496LL, &v16);
      v10 = v16;
      v11 = std::enable_shared_from_this<Spectre::Engine::Scene>::shared_from_this(v9 + 8, &v14);
      Spectre::Engine::DeviceResource::SetDevice(v10, v11);
      if ( v15 )
        std::_Ref_count_base::_Decref(v15);
      if ( !(*(unsigned __int8 (__fastcall **)(__int64, _QWORD, _QWORD, __int64, __int64))(*(_QWORD *)v16 + 40LL))(
              v16,
              a1[4],
              ((unsigned int)a1[5] - (unsigned int)a1[4]) & 0xFFFFFFFC,
              2,
              a1[2] + 16LL) )
      {
        std::string::string(v20, "ShaderPropertyBlock::AttachDevice() -- failed to create constant buffer");
        v12 = std::string::string(
                v19,
                "onecoreuap\\windows\\dwm\\spectre\\engine\\products\\components\\nativerenderer\\cpp\\source\\engine\\sh"
                "aderpropertyblock.cpp");
        Spectre::Engine::EngineInvalidArgException::EngineInvalidArgException(
          (unsigned int)pExceptionObject,
          v12,
          v13,
          (unsigned int)v20,
          0);
        throw (Spectre::Engine::EngineInvalidArgException *)pExceptionObject;
      }
      Spectre::Engine::ConstantBuffer::AttachDeviceConstantBuffer(a1[16], &v16);
      LODWORD(v14) = v8;
      *(_DWORD *)(*(_QWORD *)std::map<enum Spectre::Engine::RenderDeviceID,unsigned int>::_Try_emplace<enum Spectre::Engine::RenderDeviceID const &,>(
                               a1 + 11,
                               v19,
                               &v14)
                + 32LL) = 0;
      if ( v17 )
        std::_Ref_count_base::_Decref(v17);
    }
    v4 = (std::_Ref_count_base *)a2[1];
  }
  if ( v4 )
    std::_Ref_count_base::_Decref(v4);
}

```

## disassembly

```asm
0x18007b480  mov     [rsp-8+arg_10], rbx
0x18007b485  push    rbp
0x18007b486  push    rsi
0x18007b487  push    rdi
0x18007b488  push    r14
0x18007b48a  push    r15
0x18007b48c  lea     rbp, [rsp-37h]
0x18007b491  sub     rsp, 0E0h
0x18007b498  mov     rax, cs:__security_cookie
0x18007b49f  xor     rax, rsp
0x18007b4a2  mov     [rbp+57h+var_28], rax
0x18007b4a6  mov     rsi, rdx
0x18007b4a9  mov     r14, rcx
0x18007b4ac  mov     [rbp+57h+var_A8], rdx
0x18007b4b0  xor     ebx, ebx
0x18007b4b2  mov     [rbp+57h+var_D0], ebx
0x18007b4b5  mov     rcx, [rdx]
0x18007b4b8  cmp     [rcx+0F4h], ebx
0x18007b4be  jnz     short loc_18007B4C9
0x18007b4c0  mov     rcx, [rdx+8]
0x18007b4c4  jmp     loc_18007B669
0x18007b4c9  mov     rax, [r14+28h]
0x18007b4cd  cmp     [r14+20h], rax
0x18007b4d1  jz      short loc_18007B4C0
0x18007b4d3  add     rcx, 18h; this
0x18007b4d7  call    ?VerifyWriteAccess@Lockable@Engine@Spectre@@QEBAXXZ; Spectre::Engine::Lockable::VerifyWriteAccess(void)
0x18007b4dc  cmp     qword ptr [r14+80h], 0
0x18007b4e4  jnz     short loc_18007B546
0x18007b4e6  mov     rcx, [rsi]
0x18007b4e9  lea     rdx, [rbp+57h+var_C8]
0x18007b4ed  mov     rcx, [rcx+0F90h]
0x18007b4f4  call    ??$CreateResource@VConstantBuffer@Engine@Spectre@@$$V@Engine@0Spectre@@QEAA?AV?$shared_ptr@VConstantBuffer@Engine@Spectre@@@std@@W4ResourceDevicePolicy@01@@Z; Spectre::Engine::Engine::CreateResource<Spectre::Engine::ConstantBuffer,>(Spectre::Engine::ResourceDevicePolicy)
0x18007b4f9  mov     ebx, 1
0x18007b4fe  mov     [rbp+57h+var_D0], ebx
0x18007b501  mov     rax, [rbp+57h+var_C8]
0x18007b505  mov     rdx, [rbp+57h+var_C0]
0x18007b509  mov     [rbp+57h+var_C8], 0
0x18007b511  mov     [rbp+57h+var_C0], 0
0x18007b519  mov     [r14+80h], rax
0x18007b520  mov     rcx, [r14+88h]; this
0x18007b527  mov     [r14+88h], rdx
0x18007b52e  test    rcx, rcx
0x18007b531  jz      short loc_18007B546
0x18007b533  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18007b538  mov     rcx, [rbp+57h+var_C0]; this
0x18007b53c  test    rcx, rcx
0x18007b53f  jz      short loc_18007B546
0x18007b541  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18007b546  mov     rax, [rsi]
0x18007b549  mov     r15d, [rax+0F4h]
0x18007b550  mov     edx, r15d
0x18007b553  mov     rcx, [r14+80h]
0x18007b55a  call    ?Contains@ConstantBuffer@Engine@Spectre@@QEBA_NW4RenderDeviceID@23@@Z; Spectre::Engine::ConstantBuffer::Contains(Spectre::Engine::RenderDeviceID)
0x18007b55f  test    al, al
0x18007b561  jnz     loc_18007B665
0x18007b567  mov     rdi, [rsi]
0x18007b56a  lea     rcx, [rdi+1F0h]
0x18007b571  lea     rdx, [rbp+57h+var_B8]
0x18007b575  call    ??$CreateResource@VDeviceConstantBuffer@Engine@Spectre@@@ResourceFactory@Engine@Spectre@@QEBA?AV?$shared_ptr@VDeviceConstantBuffer@Engine@Spectre@@@std@@XZ; Spectre::Engine::ResourceFactory::CreateResource<Spectre::Engine::DeviceConstantBuffer>(void)
0x18007b57a  or      ebx, 2
0x18007b57d  mov     [rbp+57h+var_D0], ebx
0x18007b580  mov     rbx, [rbp+57h+var_B8]
0x18007b584  lea     rcx, [rdi+8]
0x18007b588  lea     rdx, [rbp+57h+var_C8]
0x18007b58c  call    ?shared_from_this@?$enable_shared_from_this@VScene@Engine@Spectre@@@std@@QEAA?AV?$shared_ptr@VScene@Engine@Spectre@@@2@XZ; std::enable_shared_from_this<Spectre::Engine::Scene>::shared_from_this(void)
0x18007b591  mov     rdx, rax
0x18007b594  mov     rcx, rbx
0x18007b597  call    ?SetDevice@DeviceResource@Engine@Spectre@@IEAAXAEBV?$shared_ptr@VRenderDevice@Engine@Spectre@@@std@@@Z; Spectre::Engine::DeviceResource::SetDevice(std::shared_ptr<Spectre::Engine::RenderDevice> const &)
0x18007b59c  mov     rcx, [rbp+57h+var_C0]; this
0x18007b5a0  test    rcx, rcx
0x18007b5a3  jz      short loc_18007B5AA
0x18007b5a5  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18007b5aa  mov     rcx, [rbp+57h+var_B8]
0x18007b5ae  mov     rdx, [r14+20h]
0x18007b5b2  mov     rax, [rcx]
0x18007b5b5  mov     r10, [r14+10h]
0x18007b5b9  add     r10, 10h
0x18007b5bd  mov     r8, [r14+28h]
0x18007b5c1  sub     r8, rdx
0x18007b5c4  and     r8d, 0FFFFFFFCh
0x18007b5c8  mov     [rsp+100h+var_E0], r10
0x18007b5cd  mov     r9d, 2
0x18007b5d3  mov     rax, [rax+28h]
0x18007b5d7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007b5dc  test    al, al
0x18007b5de  jnz     short loc_18007B627
0x18007b5e0  lea     rdx, aShaderproperty_13; "ShaderPropertyBlock::AttachDevice() -- "...
0x18007b5e7  lea     rcx, [rbp+57h+var_80]
0x18007b5eb  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x18007b5f0  nop
0x18007b5f1  lea     rdx, aOnecoreuapWind_39; "onecoreuap\\windows\\dwm\\spectre\\engi"...
0x18007b5f8  lea     rcx, [rbp+57h+var_A0]
0x18007b5fc  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x18007b601  mov     byte ptr [rsp+100h+var_E0], 0
0x18007b606  lea     r9, [rbp+57h+var_80]
0x18007b60a  mov     rdx, rax
0x18007b60d  lea     rcx, [rbp+57h+pExceptionObject]
0x18007b611  call    ??0EngineInvalidArgException@Engine@Spectre@@QEAA@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@HAEBV34@_N@Z; Spectre::Engine::EngineInvalidArgException::EngineInvalidArgException(std::string,int,std::string const &,bool)
0x18007b616  lea     rdx, _TI5?AUEngineInvalidArgException@Engine@Spectre@@; pThrowInfo
0x18007b61d  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x18007b621  call    _CxxThrowException_0
0x18007b627  lea     rdx, [rbp+57h+var_B8]
0x18007b62b  mov     rcx, [r14+80h]
0x18007b632  call    ?AttachDeviceConstantBuffer@ConstantBuffer@Engine@Spectre@@QEAAXAEBV?$shared_ptr@VDeviceConstantBuffer@Engine@Spectre@@@std@@@Z; Spectre::Engine::ConstantBuffer::AttachDeviceConstantBuffer(std::shared_ptr<Spectre::Engine::DeviceConstantBuffer> const &)
0x18007b637  mov     dword ptr [rbp+57h+var_C8], r15d
0x18007b63b  lea     rcx, [r14+58h]
0x18007b63f  lea     r8, [rbp+57h+var_C8]
0x18007b643  lea     rdx, [rbp+57h+var_A0]
0x18007b647  call    ??$_Try_emplace@AEBW4RenderDeviceID@Engine@Spectre@@$$V@?$map@W4RenderDeviceID@Engine@Spectre@@IU?$less@W4RenderDeviceID@Engine@Spectre@@@std@@V?$allocator@U?$pair@$$CBW4RenderDeviceID@Engine@Spectre@@I@std@@@5@@std@@AEAA?AU?$pair@PEAU?$_Tree_node@U?$pair@$$CBW4RenderDeviceID@Engine@Spectre@@I@std@@PEAX@std@@_N@1@AEBW4RenderDeviceID@Engine@Spectre@@@Z; std::map<Spectre::Engine::RenderDeviceID,uint>::_Try_emplace<Spectre::Engine::RenderDeviceID const &,>(Spectre::Engine::RenderDeviceID const &)
0x18007b64c  mov     rcx, [rax]
0x18007b64f  mov     dword ptr [rcx+20h], 0
0x18007b656  mov     rcx, [rbp+57h+var_B0]; this
0x18007b65a  test    rcx, rcx
0x18007b65d  jz      short loc_18007B665
0x18007b65f  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18007b664  nop
0x18007b665  mov     rcx, [rsi+8]; this
0x18007b669  test    rcx, rcx
0x18007b66c  jz      short loc_18007B673
0x18007b66e  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18007b673  mov     rcx, [rbp+57h+var_28]
0x18007b677  xor     rcx, rsp; StackCookie
0x18007b67a  call    __security_check_cookie
0x18007b67f  mov     rbx, [rsp+100h+arg_10]
0x18007b687  add     rsp, 0E0h
0x18007b68e  pop     r15
0x18007b690  pop     r14
0x18007b692  pop     rdi
0x18007b693  pop     rsi
0x18007b694  pop     rbp
0x18007b695  retn
```
