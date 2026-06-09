# Spectre::Engine::GpuProfilerFrame::MarkerQueryData::EndTimeSpan(void)

- ea: `0x180096c80`
- end: `0x180096df2`
- name: `?EndTimeSpan@MarkerQueryData@GpuProfilerFrame@Engine@Spectre@@UEAAXXZ`
- size: `370`
- prototype: `void __fastcall(Spectre::Engine::GpuProfilerFrame::MarkerQueryData *__hidden this)`
- caller_count: `0`
- callee_count: `17`
- tags: `broker_com_uri`

## callees

- `0x18000ca90`
- `0x18000dfa2`
- `0x18001128c`
- `0x180011f64`
- `0x180012df8`
- `0x180025cf4`
- `0x1800289ac`
- `0x180028b24`
- `0x1800681a8`
- `0x1800959c0`
- `0x180095a48`
- `0x180095aa4`
- `0x180095bf4`
- `0x180095c90`
- `0x180095d28`
- `0x180096c80`
- `0x1800e7010`

## string_xrefs

- `0x180096cba`: `Attempt to call EndTimeSpan() on a query marker that wasn't a timespan.`
- `0x180096ccb`: `onecoreuap\windows\dwm\spectre\engine\products\components\nativerenderer\cpp\source\engine\gpuprofiler\gpuprofilerframe.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
void __fastcall Spectre::Engine::GpuProfilerFrame::MarkerQueryData::EndTimeSpan(
        Spectre::Engine::GpuProfilerFrame::MarkerQueryData *this)
{
  Spectre::Utils::SharedMutex *v2; // rsi
  int v3; // eax
  int v4; // r8d
  char *v5; // rdi
  _QWORD *CommandList; // rax
  __int64 Query; // rax
  char *v8; // rbx
  __int64 v9; // rax
  _BYTE v10[32]; // [rsp+40h] [rbp-C0h] BYREF
  _BYTE v11[176]; // [rsp+60h] [rbp-A0h] BYREF
  _BYTE v12[8]; // [rsp+110h] [rbp+10h] BYREF
  std::_Ref_count_base *v13; // [rsp+118h] [rbp+18h]
  _BYTE pExceptionObject[56]; // [rsp+130h] [rbp+30h] BYREF

  v2 = (Spectre::Engine::GpuProfilerFrame::MarkerQueryData *)((char *)this + 8);
  Spectre::Engine::Mutex::doLock<&public: void Spectre::Utils::SharedMutex::lock(void)>((Spectre::Engine::GpuProfilerFrame::MarkerQueryData *)((char *)this + 8));
  if ( *((_DWORD *)this + 4) != 1 )
  {
    std::string::string(v12, "Attempt to call EndTimeSpan() on a query marker that wasn't a timespan.");
    v3 = std::string::string(
           v10,
           "onecoreuap\\windows\\dwm\\spectre\\engine\\products\\components\\nativerenderer\\cpp\\source\\engine\\gpuprof"
           "iler\\gpuprofilerframe.cpp");
    Spectre::Engine::EngineException::EngineException((unsigned int)pExceptionObject, v3, v4, (unsigned int)v12, 0);
    throw (Spectre::Engine::EngineException *)pExceptionObject;
  }
  v5 = (char *)this + 32;
  if ( (unsigned __int8)Spectre::Engine::RenderDeviceQuery::operator bool((char *)this + 32) )
  {
    CommandList = (_QWORD *)Spectre::Engine::RenderDeviceQuery::GetCommandList((char *)this + 32, v12);
    (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*CommandList + 72LL))(*CommandList);
    if ( v13 )
      std::_Ref_count_base::_Decref(v13);
    Query = Spectre::Engine::RenderDevice::GetQuery(*((_QWORD *)this + 3), v11, 1);
    v8 = (char *)this + 216;
    Spectre::Engine::RenderDeviceQuery::operator=(v8, Query);
    Spectre::Engine::RenderDeviceQuery::~RenderDeviceQuery((Spectre::Engine::RenderDeviceQuery *)v11);
    if ( (unsigned __int8)Spectre::Engine::RenderDeviceQuery::operator bool(v8) )
    {
      std::shared_ptr<Spectre::Engine::ISceneNodeTraversal>::shared_ptr<Spectre::Engine::ISceneNodeTraversal>(
        v12,
        v5 + 160);
      v9 = Spectre::Engine::RenderDeviceQuery::GetCommandList(v5, v10);
      Spectre::Engine::RenderDeviceQuery::End(v8, v9, v12);
    }
    else
    {
      Spectre::Engine::RenderDeviceQuery::RenderDeviceQuery((Spectre::Engine::RenderDeviceQuery *)v11);
      Spectre::Engine::RenderDeviceQuery::operator=(v5, v11);
      Spectre::Engine::RenderDeviceQuery::~RenderDeviceQuery((Spectre::Engine::RenderDeviceQuery *)v11);
    }
  }
  Spectre::Engine::Mutex::doUnlock<&public: void Spectre::Utils::SharedMutex::unlock(void)>(v2);
}

```

## disassembly

```asm
0x180096c80  push    rbp
0x180096c82  push    rbx
0x180096c83  push    rsi
0x180096c84  push    rdi
0x180096c85  lea     rbp, [rsp-78h]
0x180096c8a  sub     rsp, 178h
0x180096c91  mov     rax, cs:__security_cookie
0x180096c98  xor     rax, rsp
0x180096c9b  mov     [rbp+90h+var_28], rax
0x180096c9f  mov     rbx, rcx
0x180096ca2  lea     rsi, [rcx+8]
0x180096ca6  mov     [rsp+190h+var_158], rsi
0x180096cab  mov     rcx, rsi; this
0x180096cae  call    ??$doLock@$1?lock@SharedMutex@Utils@Spectre@@QEAAXXZ@Mutex@Engine@Spectre@@AEAAX_N@Z; Spectre::Engine::Mutex::doLock<&Spectre::Utils::SharedMutex::lock(void)>(bool)
0x180096cb3  nop
0x180096cb4  cmp     dword ptr [rbx+10h], 1
0x180096cb8  jz      short loc_180096D02
0x180096cba  lea     rdx, aAttemptToCallE; "Attempt to call EndTimeSpan() on a quer"...
0x180096cc1  lea     rcx, [rbp+90h+var_80]
0x180096cc5  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x180096cca  nop
0x180096ccb  lea     rdx, aOnecoreuapWind_48; "onecoreuap\\windows\\dwm\\spectre\\engi"...
0x180096cd2  lea     rcx, [rsp+190h+var_150]
0x180096cd7  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x180096cdc  mov     [rsp+190h+var_170], 0
0x180096ce1  lea     r9, [rbp+90h+var_80]
0x180096ce5  mov     rdx, rax
0x180096ce8  lea     rcx, [rbp+90h+pExceptionObject]
0x180096cec  call    ??0EngineException@Engine@Spectre@@QEAA@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@HAEBV34@_N@Z; Spectre::Engine::EngineException::EngineException(std::string,int,std::string const &,bool)
0x180096cf1  lea     rdx, _TI4?AUEngineException@Engine@Spectre@@; pThrowInfo
0x180096cf8  lea     rcx, [rbp+90h+pExceptionObject]; pExceptionObject
0x180096cfc  call    _CxxThrowException_0
0x180096d02  lea     rdi, [rbx+20h]
0x180096d06  mov     rcx, rdi
0x180096d09  call    ??BRenderDeviceQuery@Engine@Spectre@@QEBA_NXZ; Spectre::Engine::RenderDeviceQuery::operator bool(void)
0x180096d0e  test    al, al
0x180096d10  jz      loc_180096DD1
0x180096d16  lea     rdx, [rbp+90h+var_80]
0x180096d1a  mov     rcx, rdi
0x180096d1d  call    ?GetCommandList@RenderDeviceQuery@Engine@Spectre@@QEBA?AV?$shared_ptr@VCommandList@Engine@Spectre@@@std@@XZ; Spectre::Engine::RenderDeviceQuery::GetCommandList(void)
0x180096d22  nop
0x180096d23  mov     rcx, [rax]
0x180096d26  mov     rax, [rcx]
0x180096d29  mov     rax, [rax+48h]
0x180096d2d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180096d32  nop
0x180096d33  mov     rcx, [rbp+90h+var_78]; this
0x180096d37  test    rcx, rcx
0x180096d3a  jz      short loc_180096D41
0x180096d3c  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180096d41  mov     r8d, 1
0x180096d47  lea     rdx, [rsp+190h+var_130]
0x180096d4c  mov     rcx, [rbx+18h]
0x180096d50  call    ?GetQuery@RenderDevice@Engine@Spectre@@QEAA?AVRenderDeviceQuery@23@W4QueryType@GpuQuery@23@@Z; Spectre::Engine::RenderDevice::GetQuery(Spectre::Engine::GpuQuery::QueryType)
0x180096d55  nop
0x180096d56  add     rbx, 0D8h
0x180096d5d  mov     rdx, rax
0x180096d60  mov     rcx, rbx
0x180096d63  call    ??4RenderDeviceQuery@Engine@Spectre@@QEAAAEAV012@$$QEAV012@@Z; Spectre::Engine::RenderDeviceQuery::operator=(Spectre::Engine::RenderDeviceQuery &&)
0x180096d68  nop
0x180096d69  lea     rcx, [rsp+190h+var_130]; this
0x180096d6e  call    ??1RenderDeviceQuery@Engine@Spectre@@QEAA@XZ; Spectre::Engine::RenderDeviceQuery::~RenderDeviceQuery(void)
0x180096d73  mov     rcx, rbx
0x180096d76  call    ??BRenderDeviceQuery@Engine@Spectre@@QEBA_NXZ; Spectre::Engine::RenderDeviceQuery::operator bool(void)
0x180096d7b  test    al, al
0x180096d7d  jz      short loc_180096DAD
0x180096d7f  lea     rdx, [rdi+0A0h]
0x180096d86  lea     rcx, [rbp+90h+var_80]
0x180096d8a  call    ??$?0VDefaultSceneNodeTraversal@Engine@Spectre@@$0A@@?$shared_ptr@VISceneNodeTraversal@Engine@Spectre@@@std@@QEAA@AEBV?$shared_ptr@VDefaultSceneNodeTraversal@Engine@Spectre@@@1@@Z; std::shared_ptr<Spectre::Engine::ISceneNodeTraversal>::shared_ptr<Spectre::Engine::ISceneNodeTraversal>(std::shared_ptr<Spectre::Engine::DefaultSceneNodeTraversal> const &)
0x180096d8f  lea     rdx, [rsp+190h+var_150]
0x180096d94  mov     rcx, rdi
0x180096d97  call    ?GetCommandList@RenderDeviceQuery@Engine@Spectre@@QEBA?AV?$shared_ptr@VCommandList@Engine@Spectre@@@std@@XZ; Spectre::Engine::RenderDeviceQuery::GetCommandList(void)
0x180096d9c  lea     r8, [rbp+90h+var_80]
0x180096da0  mov     rdx, rax
0x180096da3  mov     rcx, rbx
0x180096da6  call    ?End@RenderDeviceQuery@Engine@Spectre@@QEAAXV?$shared_ptr@VCommandList@Engine@Spectre@@@std@@0@Z; Spectre::Engine::RenderDeviceQuery::End(std::shared_ptr<Spectre::Engine::CommandList>,std::shared_ptr<Spectre::Engine::CommandList>)
0x180096dab  jmp     short loc_180096DD1
0x180096dad  lea     rcx, [rsp+190h+var_130]; this
0x180096db2  call    ??0RenderDeviceQuery@Engine@Spectre@@QEAA@XZ; Spectre::Engine::RenderDeviceQuery::RenderDeviceQuery(void)
0x180096db7  nop
0x180096db8  lea     rdx, [rsp+190h+var_130]
0x180096dbd  mov     rcx, rdi
0x180096dc0  call    ??4RenderDeviceQuery@Engine@Spectre@@QEAAAEAV012@$$QEAV012@@Z; Spectre::Engine::RenderDeviceQuery::operator=(Spectre::Engine::RenderDeviceQuery &&)
0x180096dc5  nop
0x180096dc6  lea     rcx, [rsp+190h+var_130]; this
0x180096dcb  call    ??1RenderDeviceQuery@Engine@Spectre@@QEAA@XZ; Spectre::Engine::RenderDeviceQuery::~RenderDeviceQuery(void)
0x180096dd0  nop
0x180096dd1  mov     rcx, rsi; this
0x180096dd4  call    ??$doUnlock@$1?unlock@SharedMutex@Utils@Spectre@@QEAAXXZ@Mutex@Engine@Spectre@@AEAAX_N@Z; Spectre::Engine::Mutex::doUnlock<&Spectre::Utils::SharedMutex::unlock(void)>(bool)
0x180096dd9  nop
0x180096dda  mov     rcx, [rbp+90h+var_28]
0x180096dde  xor     rcx, rsp; StackCookie
0x180096de1  call    __security_check_cookie
0x180096de6  add     rsp, 178h
0x180096ded  pop     rdi
0x180096dee  pop     rsi
0x180096def  pop     rbx
0x180096df0  pop     rbp
0x180096df1  retn
```
