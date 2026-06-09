# LoadIsoDll(_RTL_RUN_ONCE *,void *,void * *)

- ea: `0x180006140`
- end: `0x1800061a0`
- name: `?LoadIsoDll@@YAHPEAT_RTL_RUN_ONCE@@PEAXPEAPEAX@Z`
- size: `96`
- prototype: `BOOL __stdcall(PINIT_ONCE InitOnce, PVOID Parameter, PVOID *Context)`
- caller_count: `0`
- callee_count: `5`
- tags: `loader_planting, installer_update`

## callees

- `0x180005310`
- `0x180006140`
- `0x1800061a8`
- `0x18000649c`
- `0x18000668c`

## import_xrefs

- `iertutil!__imp_?InternalForkingSupport_ShouldUseEdge@@YA?B_NXZ` at `0x180006151`
- `iertutil!__imp_?InternalForkingSupport_ShouldUseEdge@@YA?B_NXZ` at `0x180006151`

## string_xrefs

- `0x180006159`: `edgeiso.dll`
- `0x180006160`: `msiso.dll`

## pseudocode

```c
__int64 __fastcall LoadIsoDll(PINIT_ONCE InitOnce, PVOID Parameter, PVOID *Context)
{
  bool ShouldUseEdge; // bl
  const CHAR *v4; // rcx
  HMODULE ModuleWithFailureDiagnosis; // rdi
  bool v6; // dl

  g_IsIsoLoaded = 1;
  ShouldUseEdge = InternalForkingSupport_ShouldUseEdge();
  v4 = "edgeiso.dll";
  if ( !ShouldUseEdge )
    v4 = "msiso.dll";
  ModuleWithFailureDiagnosis = LoadModuleWithFailureDiagnosis(v4);
  LoadSharedApis(ModuleWithFailureDiagnosis, v6);
  if ( ShouldUseEdge )
    LoadEdgeApis(ModuleWithFailureDiagnosis);
  else
    LoadLegacyApis(ModuleWithFailureDiagnosis);
  return 1;
}

```

## disassembly

```asm
0x180006140  mov     [rsp+arg_0], rbx
0x180006145  push    rdi
0x180006146  sub     rsp, 20h
0x18000614a  mov     cs:?g_IsIsoLoaded@@3_NC, 1; bool volatile g_IsIsoLoaded
0x180006151  call    cs:__imp_?InternalForkingSupport_ShouldUseEdge@@YA?B_NXZ; InternalForkingSupport_ShouldUseEdge(void)
0x180006157  mov     bl, al
0x180006159  lea     rcx, aEdgeisoDll; "edgeiso.dll"
0x180006160  lea     rax, aMsisoDll; "msiso.dll"
0x180006167  test    bl, bl
0x180006169  cmovz   rcx, rax
0x18000616d  call    LoadModuleWithFailureDiagnosis
0x180006172  mov     rcx, rax; hModule
0x180006175  mov     rdi, rax
0x180006178  call    ?LoadSharedApis@@YAXPEAUHINSTANCE__@@_N@Z; LoadSharedApis(HINSTANCE__ *,bool)
0x18000617d  mov     rcx, rdi; hModule
0x180006180  test    bl, bl
0x180006182  jz      short loc_18000618B
0x180006184  call    ?LoadEdgeApis@@YAXPEAUHINSTANCE__@@@Z; LoadEdgeApis(HINSTANCE__ *)
0x180006189  jmp     short loc_180006190
0x18000618b  call    ?LoadLegacyApis@@YAXPEAUHINSTANCE__@@@Z; LoadLegacyApis(HINSTANCE__ *)
0x180006190  mov     rbx, [rsp+28h+arg_0]
0x180006195  mov     eax, 1
0x18000619a  add     rsp, 20h
0x18000619e  pop     rdi
0x18000619f  retn
```
