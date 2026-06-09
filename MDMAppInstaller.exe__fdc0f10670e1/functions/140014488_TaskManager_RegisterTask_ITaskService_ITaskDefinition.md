# TaskManager::RegisterTask(ITaskService *,ITaskDefinition *)

- ea: `0x140014488`
- end: `0x14001465b`
- name: `?RegisterTask@TaskManager@@CAJPEAUITaskService@@PEAUITaskDefinition@@@Z`
- size: `467`
- prototype: `__int64 __fastcall(struct ITaskService *, struct ITaskDefinition *)`
- caller_count: `2`
- callee_count: `4`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x140013c90`
- `0x140015108`

## callees

- `0x14000740c`
- `0x140014174`
- `0x140014488`
- `0x14001c010`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x140014532`
- `OLEAUT32!__imp_SysAllocString` at `0x140014551`
- `OLEAUT32!__imp_SysAllocString` at `0x140014532`
- `OLEAUT32!__imp_SysAllocString` at `0x140014551`
- `OLEAUT32!__imp_SysFreeString` at `0x14001461f`
- `OLEAUT32!__imp_SysFreeString` at `0x14001461f`
- `OLEAUT32!__imp_VariantInit` at `0x1400144d4`
- `OLEAUT32!__imp_VariantInit` at `0x1400144de`
- `OLEAUT32!__imp_VariantInit` at `0x1400144d4`
- `OLEAUT32!__imp_VariantInit` at `0x1400144de`
- `OLEAUT32!__imp_VariantClear` at `0x140014629`
- `OLEAUT32!__imp_VariantClear` at `0x140014629`

## string_xrefs

- `0x140014635`: `RegisterTask() failed.  Error = 0x%1!x!.`
- `0x140014546`: `Resume App Installation Actions`

## pseudocode

```c
__int64 __fastcall TaskManager::RegisterTask(struct ITaskService *a1, struct ITaskDefinition *a2)
{
  struct ITaskFolder *v3; // rdi
  OLECHAR *v5; // rsi
  int v6; // ebx
  int TaskFolder; // eax
  struct ITaskFolderVtbl *lpVtbl; // rax
  HRESULT (__stdcall *RegisterTaskDefinition)(ITaskFolder *, BSTR, ITaskDefinition *, LONG, VARIANT, VARIANT, TASK_LOGON_TYPE, VARIANT, IRegisteredTask **); // rax
  int v10; // eax
  VARIANTARG v12; // [rsp+50h] [rbp-49h] BYREF
  VARIANTARG pvarg; // [rsp+68h] [rbp-31h] BYREF
  __int128 v14; // [rsp+80h] [rbp-19h] BYREF
  IRecordInfo *pRecInfo; // [rsp+90h] [rbp-9h]
  VARIANTARG v16; // [rsp+A0h] [rbp+7h] BYREF
  VARIANTARG v17; // [rsp+C0h] [rbp+27h] BYREF
  __int64 v18; // [rsp+100h] [rbp+67h] BYREF
  struct ITaskFolder *v19; // [rsp+110h] [rbp+77h] BYREF

  v18 = 0;
  v3 = 0;
  v19 = 0;
  v5 = 0;
  memset(&pvarg, 0, sizeof(pvarg));
  memset(&v12, 0, sizeof(v12));
  VariantInit(&pvarg);
  VariantInit(&v12);
  if ( a1 && a2 )
  {
    TaskFolder = TaskManager::GetTaskFolder(a1, L"Microsoft\\Windows\\EnterpriseMgmt\\DesktopAppCSP", 1, &v19);
    v3 = v19;
    v6 = TaskFolder;
    if ( TaskFolder >= 0 )
    {
      if ( v19
        && (v12.llVal = (LONGLONG)SysAllocString(L"S-1-5-18")) != 0
        && (v12.vt = 8, (v5 = SysAllocString(L"Resume App Installation Actions")) != 0) )
      {
        lpVtbl = v3->lpVtbl;
        pRecInfo = pvarg.pRecInfo;
        RegisterTaskDefinition = lpVtbl->RegisterTaskDefinition;
        v16 = pvarg;
        v14 = *(_OWORD *)&pvarg.vt;
        v17 = v12;
        v10 = ((__int64 (__fastcall *)(struct ITaskFolder *, OLECHAR *, struct ITaskDefinition *, __int64, VARIANTARG *, VARIANTARG *, int, __int128 *, __int64 *))RegisterTaskDefinition)(
                v3,
                v5,
                a2,
                6,
                &v17,
                &v16,
                5,
                &v14,
                &v18);
        v6 = v10;
        if ( v10 >= 0 )
        {
          if ( !v18 )
            v10 = -2147024882;
          v6 = v10;
        }
      }
      else
      {
        v6 = -2147024882;
      }
    }
  }
  else
  {
    v6 = -2147024809;
  }
  if ( v18 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v18 + 16LL))(v18);
    v18 = 0;
  }
  if ( v3 )
    ((void (__fastcall *)(struct ITaskFolder *))v3->lpVtbl->Release)(v3);
  SysFreeString(v5);
  VariantClear(&v12);
  if ( v6 < 0 )
    LogError(L"RegisterTask() failed.  Error = 0x%1!x!.", (unsigned int)v6);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x140014488  mov     [rsp-8+arg_8], rbx
0x14001448d  mov     [rsp-8+arg_18], rsi
0x140014492  push    rbp
0x140014493  push    rdi
0x140014494  push    r14
0x140014496  lea     rbp, [rsp-47h]
0x14001449b  sub     rsp, 0E0h
0x1400144a2  xor     eax, eax
0x1400144a4  mov     [rbp+57h+arg_0], 0
0x1400144ac  mov     rbx, rcx
0x1400144af  mov     qword ptr [rbp+57h+pvarg+10h], rax
0x1400144b3  xorps   xmm0, xmm0
0x1400144b6  mov     qword ptr [rbp+57h+var_A0+10h], rax
0x1400144ba  xorps   xmm1, xmm1
0x1400144bd  lea     rcx, [rbp+57h+pvarg]; pvarg
0x1400144c1  xor     edi, edi
0x1400144c3  mov     r14, rdx
0x1400144c6  mov     [rbp+57h+arg_10], rdi
0x1400144ca  xor     esi, esi
0x1400144cc  movups  xmmword ptr [rbp+57h+pvarg], xmm0
0x1400144d0  movups  xmmword ptr [rbp+57h+var_A0], xmm1
0x1400144d4  call    cs:__imp_VariantInit
0x1400144da  lea     rcx, [rbp+57h+var_A0]; pvarg
0x1400144de  call    cs:__imp_VariantInit
0x1400144e4  test    rbx, rbx
0x1400144e7  jnz     short loc_1400144F3
0x1400144e9  mov     ebx, 80070057h
0x1400144ee  jmp     loc_1400145EB
0x1400144f3  test    r14, r14
0x1400144f6  jz      short loc_1400144E9
0x1400144f8  lea     r9, [rbp+57h+arg_10]; struct ITaskFolder **
0x1400144fc  mov     r8b, 1; bool
0x1400144ff  lea     rdx, aMicrosoftWindo; "Microsoft\\Windows\\EnterpriseMgmt\\Des"...
0x140014506  mov     rcx, rbx; struct ITaskService *
0x140014509  call    ?GetTaskFolder@TaskManager@@CAJPEAUITaskService@@PEBG_NPEAPEAUITaskFolder@@@Z; TaskManager::GetTaskFolder(ITaskService *,ushort const *,bool,ITaskFolder * *)
0x14001450e  mov     rdi, [rbp+57h+arg_10]
0x140014512  mov     ebx, eax
0x140014514  test    eax, eax
0x140014516  js      loc_1400145EB
0x14001451c  test    rdi, rdi
0x14001451f  jnz     short loc_14001452B
0x140014521  mov     ebx, 8007000Eh
0x140014526  jmp     loc_1400145EB
0x14001452b  lea     rcx, aS1518_0; "S-1-5-18"
0x140014532  call    cs:__imp_SysAllocString
0x140014538  mov     qword ptr [rbp+57h+var_A0+8], rax
0x14001453c  test    rax, rax
0x14001453f  jz      short loc_140014521
0x140014541  mov     eax, 8
0x140014546  lea     rcx, psz; "Resume App Installation Actions"
0x14001454d  mov     word ptr [rbp+57h+var_A0], ax
0x140014551  call    cs:__imp_SysAllocString
0x140014557  mov     rsi, rax
0x14001455a  test    rax, rax
0x14001455d  jz      short loc_140014521
0x14001455f  movups  xmm1, xmmword ptr [rbp+57h+pvarg]
0x140014563  lea     rcx, [rbp+57h+arg_0]
0x140014567  mov     rax, [rdi]
0x14001456a  movsd   xmm0, qword ptr [rbp+57h+pvarg+10h]
0x14001456f  mov     r9d, 6
0x140014575  mov     [rsp+0F0h+var_B0], rcx
0x14001457a  mov     r8, r14
0x14001457d  lea     rcx, [rbp+57h+var_70]
0x140014581  movsd   [rbp+57h+var_60], xmm0
0x140014586  mov     rax, [rax+88h]
0x14001458d  mov     rdx, rsi
0x140014590  mov     [rsp+0F0h+var_B8], rcx
0x140014595  lea     rcx, [rbp+57h+var_50]
0x140014599  mov     [rsp+0F0h+var_C0], 5
0x1400145a1  mov     [rsp+0F0h+var_C8], rcx
0x1400145a6  lea     rcx, [rbp+57h+var_30]
0x1400145aa  movsd   [rbp+57h+var_40], xmm0
0x1400145af  movups  xmm0, xmmword ptr [rbp+57h+var_A0]
0x1400145b3  mov     [rsp+0F0h+var_D0], rcx
0x1400145b8  mov     rcx, rdi
0x1400145bb  movaps  [rbp+57h+var_70], xmm1
0x1400145bf  movaps  [rbp+57h+var_50], xmm1
0x1400145c3  movsd   xmm1, qword ptr [rbp+57h+var_A0+10h]
0x1400145c8  movaps  [rbp+57h+var_30], xmm0
0x1400145cc  movsd   [rbp+57h+var_20], xmm1
0x1400145d1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400145d6  mov     ebx, eax
0x1400145d8  test    eax, eax
0x1400145da  js      short loc_1400145EB
0x1400145dc  cmp     [rbp+57h+arg_0], 0
0x1400145e1  mov     ebx, 8007000Eh
0x1400145e6  cmovz   eax, ebx
0x1400145e9  mov     ebx, eax
0x1400145eb  mov     rcx, [rbp+57h+arg_0]
0x1400145ef  test    rcx, rcx
0x1400145f2  jz      short loc_140014608
0x1400145f4  mov     rax, [rcx]
0x1400145f7  mov     rax, [rax+10h]
0x1400145fb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140014600  mov     [rbp+57h+arg_0], 0
0x140014608  test    rdi, rdi
0x14001460b  jz      short loc_14001461C
0x14001460d  mov     rax, [rdi]
0x140014610  mov     rcx, rdi
0x140014613  mov     rax, [rax+10h]
0x140014617  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001461c  mov     rcx, rsi; bstrString
0x14001461f  call    cs:__imp_SysFreeString
0x140014625  lea     rcx, [rbp+57h+var_A0]; pvarg
0x140014629  call    cs:__imp_VariantClear
0x14001462f  test    ebx, ebx
0x140014631  jns     short loc_140014641
0x140014633  mov     edx, ebx
0x140014635  lea     rcx, aRegistertaskFa; "RegisterTask() failed.  Error = 0x%1!x!"...
0x14001463c  call    ?LogError@@YAXPEBGZZ; LogError(ushort const *,...)
0x140014641  lea     r11, [rsp+0F0h+var_10]
0x140014649  mov     eax, ebx
0x14001464b  mov     rbx, [r11+28h]
0x14001464f  mov     rsi, [r11+38h]
0x140014653  mov     rsp, r11
0x140014656  pop     r14
0x140014658  pop     rdi
0x140014659  pop     rbp
0x14001465a  retn
```
