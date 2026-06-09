# Spectre::Engine::VertexLayout::AttachDeviceVertexLayout(std::shared_ptr<Spectre::Engine::DeviceVertexLayout>)

- ea: `0x180081e48`
- end: `0x180082004`
- name: `?AttachDeviceVertexLayout@VertexLayout@Engine@Spectre@@QEAAXV?$shared_ptr@VDeviceVertexLayout@Engine@Spectre@@@std@@@Z`
- size: `444`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x180081d40`

## callees

- `0x18000ca90`
- `0x18000dfa2`
- `0x18001128c`
- `0x180011f64`
- `0x180050124`
- `0x1800681a8`
- `0x18008195c`
- `0x180081ae0`
- `0x180081e48`

## string_xrefs

- `0x180081edf`: `Attaching a device vertex layout to an incompatible vertex layout.`
- `0x180081ef0`: `onecoreuap\windows\dwm\spectre\engine\products\components\nativerenderer\cpp\source\engine\vertexlayout.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall Spectre::Engine::VertexLayout::AttachDeviceVertexLayout(__int64 a1, _QWORD *a2)
{
  __int64 v3; // rdx
  int v4; // r15d
  __int64 v5; // rsi
  char v6; // r14
  __int64 v7; // rbx
  int v8; // ecx
  char v9; // al
  int v10; // eax
  int v11; // r8d
  __int64 v12; // r8
  __int64 v13; // rax
  __int64 v14; // rdx
  std::_Ref_count_base *v15; // rcx
  __int64 v16; // rsi
  std::_Ref_count_base *v17; // rcx
  int v18; // [rsp+30h] [rbp-59h] BYREF
  _QWORD *v19; // [rsp+38h] [rbp-51h]
  _BYTE v20[32]; // [rsp+40h] [rbp-49h] BYREF
  _BYTE v21[32]; // [rsp+60h] [rbp-29h] BYREF
  _BYTE pExceptionObject[56]; // [rsp+80h] [rbp-9h] BYREF

  v19 = a2;
  v3 = *a2;
  v4 = *(_DWORD *)(v3 + 88);
  v5 = a1 + 144;
  v6 = 1;
  if ( !*(_QWORD *)(a1 + 152) || *(_DWORD *)(a1 + 152) == 1 && *(_DWORD *)(**(_QWORD **)v5 + 32LL) == v4 )
  {
    v7 = a1 + 96;
  }
  else
  {
    v7 = a1 + 96;
    v8 = *(_DWORD *)(a1 + 96);
    if ( *(_DWORD *)v7 != *(_DWORD *)(v3 + 96) )
      goto LABEL_11;
    v6 = 0;
    if ( v8 )
    {
      if ( v8 != 1 )
        goto LABEL_11;
      v9 = std::operator==<Spectre::Engine::VertexLayoutBase::VertexElementDesc,std::allocator<Spectre::Engine::VertexLayoutBase::VertexElementDesc>>(
             v7 + 16,
             v3 + 112);
    }
    else
    {
      if ( *(_QWORD *)(v7 + 8) == *(_QWORD *)(v3 + 104) )
        goto LABEL_13;
      v9 = 0;
    }
    if ( !v9 )
    {
LABEL_11:
      std::string::string(v21, "Attaching a device vertex layout to an incompatible vertex layout.");
      v10 = std::string::string(
              v20,
              "onecoreuap\\windows\\dwm\\spectre\\engine\\products\\components\\nativerenderer\\cpp\\source\\engine\\vertexlayout.cpp");
      Spectre::Engine::EngineException::EngineException((unsigned int)pExceptionObject, v10, v11, (unsigned int)v21, 0);
      throw (Spectre::Engine::EngineException *)pExceptionObject;
    }
  }
LABEL_13:
  v18 = v4;
  v12 = *(_QWORD *)std::map<enum Spectre::Engine::RenderDeviceID,std::shared_ptr<Spectre::Engine::DeviceShader>>::_Try_emplace<enum Spectre::Engine::RenderDeviceID const &,>(
                     v5,
                     v20,
                     &v18);
  v13 = *a2;
  v14 = a2[1];
  *a2 = 0;
  a2[1] = 0;
  *(_QWORD *)(v12 + 40) = v13;
  v15 = *(std::_Ref_count_base **)(v12 + 48);
  *(_QWORD *)(v12 + 48) = v14;
  if ( v15 )
    std::_Ref_count_base::_Decref(v15);
  if ( v6 )
  {
    v18 = v4;
    v16 = *(_QWORD *)(*(_QWORD *)std::map<enum Spectre::Engine::RenderDeviceID,std::shared_ptr<Spectre::Engine::DeviceShader>>::_Try_emplace<enum Spectre::Engine::RenderDeviceID const &,>(
                                   v5,
                                   v20,
                                   &v18)
                    + 40LL);
    *(_DWORD *)v7 = *(_DWORD *)(v16 + 96);
    *(_QWORD *)(v7 + 8) = *(_QWORD *)(v16 + 104);
    if ( v7 + 16 != v16 + 112 )
      std::vector<Spectre::Engine::VertexLayoutBase::VertexElementDesc>::_Assign_counted_range<Spectre::Engine::VertexLayoutBase::VertexElementDesc *>(
        v7 + 16,
        *(_QWORD *)(v16 + 112),
        0xAAAAAAAAAAAAAAABuLL * ((__int64)(*(_QWORD *)(v16 + 120) - *(_QWORD *)(v16 + 112)) >> 4));
    *(_QWORD *)(v7 + 40) = *(_QWORD *)(v16 + 136);
  }
  v17 = (std::_Ref_count_base *)a2[1];
  if ( v17 )
    std::_Ref_count_base::_Decref(v17);
}

```

## disassembly

```asm
0x180081e48  mov     [rsp-8+arg_10], rbx
0x180081e4d  push    rbp
0x180081e4e  push    rsi
0x180081e4f  push    rdi
0x180081e50  push    r14
0x180081e52  push    r15
0x180081e54  lea     rbp, [rsp-37h]
0x180081e59  sub     rsp, 0C0h
0x180081e60  mov     rax, cs:__security_cookie
0x180081e67  xor     rax, rsp
0x180081e6a  mov     [rbp+57h+var_28], rax
0x180081e6e  mov     rdi, rdx
0x180081e71  mov     rbx, rcx
0x180081e74  mov     [rbp+57h+var_A8], rdx
0x180081e78  mov     rdx, [rdx]
0x180081e7b  mov     r15d, [rdx+58h]
0x180081e7f  lea     rsi, [rcx+90h]
0x180081e86  mov     r14d, 1
0x180081e8c  cmp     qword ptr [rsi+8], 0
0x180081e91  jz      loc_180081F26
0x180081e97  cmp     [rsi+8], r14d
0x180081e9b  jnz     short loc_180081EA9
0x180081e9d  mov     rax, [rsi]
0x180081ea0  mov     rcx, [rax]
0x180081ea3  cmp     [rcx+20h], r15d
0x180081ea7  jz      short loc_180081F26
0x180081ea9  add     rbx, 60h ; '`'
0x180081ead  mov     ecx, [rbx]
0x180081eaf  cmp     ecx, [rdx+60h]
0x180081eb2  jnz     short loc_180081EDF
0x180081eb4  xor     r14b, r14b
0x180081eb7  test    ecx, ecx
0x180081eb9  jz      short loc_180081ECF
0x180081ebb  cmp     ecx, 1
0x180081ebe  jnz     short loc_180081EDF
0x180081ec0  add     rdx, 70h ; 'p'
0x180081ec4  lea     rcx, [rbx+10h]
0x180081ec8  call    ??$?8UVertexElementDesc@VertexLayoutBase@Engine@Spectre@@V?$allocator@UVertexElementDesc@VertexLayoutBase@Engine@Spectre@@@std@@@std@@YA_NAEBV?$vector@UVertexElementDesc@VertexLayoutBase@Engine@Spectre@@V?$allocator@UVertexElementDesc@VertexLayoutBase@Engine@Spectre@@@std@@@0@0@Z; std::operator==<Spectre::Engine::VertexLayoutBase::VertexElementDesc,std::allocator<Spectre::Engine::VertexLayoutBase::VertexElementDesc>>(std::vector<Spectre::Engine::VertexLayoutBase::VertexElementDesc> const &,std::vector<Spectre::Engine::VertexLayoutBase::VertexElementDesc> const &)
0x180081ecd  jmp     short loc_180081EDB
0x180081ecf  mov     rax, [rdx+68h]
0x180081ed3  cmp     [rbx+8], rax
0x180081ed7  jz      short loc_180081F2A
0x180081ed9  xor     al, al
0x180081edb  test    al, al
0x180081edd  jnz     short loc_180081F2A
0x180081edf  lea     rdx, aAttachingADevi; "Attaching a device vertex layout to an "...
0x180081ee6  lea     rcx, [rbp+57h+var_80]
0x180081eea  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x180081eef  nop
0x180081ef0  lea     rdx, aOnecoreuapWind_27; "onecoreuap\\windows\\dwm\\spectre\\engi"...
0x180081ef7  lea     rcx, [rbp+57h+var_A0]
0x180081efb  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x180081f00  mov     [rsp+0E0h+var_C0], 0
0x180081f05  lea     r9, [rbp+57h+var_80]
0x180081f09  mov     rdx, rax
0x180081f0c  lea     rcx, [rbp+57h+pExceptionObject]
0x180081f10  call    ??0EngineException@Engine@Spectre@@QEAA@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@HAEBV34@_N@Z; Spectre::Engine::EngineException::EngineException(std::string,int,std::string const &,bool)
0x180081f15  lea     rdx, _TI4?AUEngineException@Engine@Spectre@@; pThrowInfo
0x180081f1c  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x180081f20  call    _CxxThrowException_0
0x180081f26  add     rbx, 60h ; '`'
0x180081f2a  mov     [rbp+57h+var_B0], r15d
0x180081f2e  lea     r8, [rbp+57h+var_B0]
0x180081f32  lea     rdx, [rbp+57h+var_A0]
0x180081f36  mov     rcx, rsi
0x180081f39  call    ??$_Try_emplace@AEBW4RenderDeviceID@Engine@Spectre@@$$V@?$map@W4RenderDeviceID@Engine@Spectre@@V?$shared_ptr@VDeviceShader@Engine@Spectre@@@std@@U?$less@W4RenderDeviceID@Engine@Spectre@@@5@V?$allocator@U?$pair@$$CBW4RenderDeviceID@Engine@Spectre@@V?$shared_ptr@VDeviceShader@Engine@Spectre@@@std@@@std@@@5@@std@@AEAA?AU?$pair@PEAU?$_Tree_node@U?$pair@$$CBW4RenderDeviceID@Engine@Spectre@@V?$shared_ptr@VDeviceShader@Engine@Spectre@@@std@@@std@@PEAX@std@@_N@1@AEBW4RenderDeviceID@Engine@Spectre@@@Z; std::map<Spectre::Engine::RenderDeviceID,std::shared_ptr<Spectre::Engine::DeviceShader>>::_Try_emplace<Spectre::Engine::RenderDeviceID const &,>(Spectre::Engine::RenderDeviceID const &)
0x180081f3e  mov     r8, [rax]
0x180081f41  mov     rax, [rdi]
0x180081f44  mov     rdx, [rdi+8]
0x180081f48  mov     qword ptr [rdi], 0
0x180081f4f  mov     qword ptr [rdi+8], 0
0x180081f57  mov     [r8+28h], rax
0x180081f5b  mov     rcx, [r8+30h]; this
0x180081f5f  mov     [r8+30h], rdx
0x180081f63  test    rcx, rcx
0x180081f66  jz      short loc_180081F6D
0x180081f68  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180081f6d  test    r14b, r14b
0x180081f70  jz      short loc_180081FD3
0x180081f72  mov     [rbp+57h+var_B0], r15d
0x180081f76  lea     r8, [rbp+57h+var_B0]
0x180081f7a  lea     rdx, [rbp+57h+var_A0]
0x180081f7e  mov     rcx, rsi
0x180081f81  call    ??$_Try_emplace@AEBW4RenderDeviceID@Engine@Spectre@@$$V@?$map@W4RenderDeviceID@Engine@Spectre@@V?$shared_ptr@VDeviceShader@Engine@Spectre@@@std@@U?$less@W4RenderDeviceID@Engine@Spectre@@@5@V?$allocator@U?$pair@$$CBW4RenderDeviceID@Engine@Spectre@@V?$shared_ptr@VDeviceShader@Engine@Spectre@@@std@@@std@@@5@@std@@AEAA?AU?$pair@PEAU?$_Tree_node@U?$pair@$$CBW4RenderDeviceID@Engine@Spectre@@V?$shared_ptr@VDeviceShader@Engine@Spectre@@@std@@@std@@PEAX@std@@_N@1@AEBW4RenderDeviceID@Engine@Spectre@@@Z; std::map<Spectre::Engine::RenderDeviceID,std::shared_ptr<Spectre::Engine::DeviceShader>>::_Try_emplace<Spectre::Engine::RenderDeviceID const &,>(Spectre::Engine::RenderDeviceID const &)
0x180081f86  mov     rcx, [rax]
0x180081f89  mov     rsi, [rcx+28h]
0x180081f8d  mov     eax, [rsi+60h]
0x180081f90  mov     [rbx], eax
0x180081f92  mov     rax, [rsi+68h]
0x180081f96  mov     [rbx+8], rax
0x180081f9a  lea     rdx, [rsi+70h]
0x180081f9e  lea     rcx, [rbx+10h]
0x180081fa2  cmp     rcx, rdx
0x180081fa5  jz      short loc_180081FC8
0x180081fa7  mov     r8, [rdx+8]
0x180081fab  sub     r8, [rdx]
0x180081fae  sar     r8, 4
0x180081fb2  mov     rax, 0AAAAAAAAAAAAAAABh
0x180081fbc  imul    r8, rax
0x180081fc0  mov     rdx, [rdx]
0x180081fc3  call    ??$_Assign_counted_range@PEAUVertexElementDesc@VertexLayoutBase@Engine@Spectre@@@?$vector@UVertexElementDesc@VertexLayoutBase@Engine@Spectre@@V?$allocator@UVertexElementDesc@VertexLayoutBase@Engine@Spectre@@@std@@@std@@AEAAXPEAUVertexElementDesc@VertexLayoutBase@Engine@Spectre@@_K@Z; std::vector<Spectre::Engine::VertexLayoutBase::VertexElementDesc>::_Assign_counted_range<Spectre::Engine::VertexLayoutBase::VertexElementDesc *>(Spectre::Engine::VertexLayoutBase::VertexElementDesc *,unsigned __int64)
0x180081fc8  mov     rax, [rsi+88h]
0x180081fcf  mov     [rbx+28h], rax
0x180081fd3  mov     rcx, [rdi+8]; this
0x180081fd7  test    rcx, rcx
0x180081fda  jz      short loc_180081FE1
0x180081fdc  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180081fe1  mov     rcx, [rbp+57h+var_28]
0x180081fe5  xor     rcx, rsp; StackCookie
0x180081fe8  call    __security_check_cookie
0x180081fed  mov     rbx, [rsp+0E0h+arg_10]
0x180081ff5  add     rsp, 0C0h
0x180081ffc  pop     r15
0x180081ffe  pop     r14
0x180082000  pop     rdi
0x180082001  pop     rsi
0x180082002  pop     rbp
0x180082003  retn
```
