# CInterceptor_IWbemSyncProvider::Internal_Call(_tag_WmiInternalContext,IWbemServices *,long,IWbemContext *,ushort const *,ushort const *,ushort const *,IWbemClassObject *,IWbemObjectSink *)

- ea: `0x140039250`
- end: `0x140039365`
- name: `?Internal_Call@CInterceptor_IWbemSyncProvider@@UEAAJU_tag_WmiInternalContext@@PEAUIWbemServices@@JPEAUIWbemContext@@PEBG33PEAUIWbemClassObject@@PEAUIWbemObjectSink@@@Z`
- size: `277`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callees

- `0x140021434`
- `0x14002145c`
- `0x1400234b8`
- `0x140039250`
- `0x140048010`

## import_xrefs

- `wbemcomn!GetMemLogObject` at `0x140039306`
- `wbemcomn!GetMemLogObject` at `0x140039306`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x140039311`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x140039311`

## pseudocode

```c
__int64 __fastcall CInterceptor_IWbemSyncProvider::Internal_Call(
        __int64 a1,
        __int128 *a2,
        __int64 a3,
        unsigned int a4,
        __int64 a5,
        __int64 a6,
        __int64 a7,
        __int64 a8,
        __int64 a9,
        __int64 a10)
{
  __int128 v10; // xmm0
  int v14; // ebx
  __int64 v15; // rcx
  CMemoryLog *MemLogObject; // rax
  struct IServerSecurity *v18; // [rsp+50h] [rbp-20h] BYREF
  struct IUnknown *v19; // [rsp+58h] [rbp-18h] BYREF
  __int128 v20; // [rsp+60h] [rbp-10h] BYREF
  int v21; // [rsp+98h] [rbp+28h] BYREF

  v10 = *a2;
  v21 = 0;
  v19 = 0;
  v18 = 0;
  v20 = v10;
  v14 = ProviderSubSystem_Globals::Begin_IdentifyCall_PrvHost((void **)&v20, &v21, &v19, &v18);
  if ( v14 < 0
    || (v14 = (*(__int64 (__fastcall **)(__int64, __int64, _QWORD, __int64, __int64, __int64, __int64, __int64, __int64))(*(_QWORD *)(a1 - 8) + 64LL))(
                a1 - 8,
                a3,
                a4,
                a5,
                a6,
                a7,
                a8,
                a9,
                a10),
        ProviderSubSystem_Globals::End_IdentifyCall_PrvHost(v15, &v19, &v18, &v21),
        v14 < 0) )
  {
    MemLogObject = GetMemLogObject();
    CMemoryLog::Write(MemLogObject, v14);
  }
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      66,
      WPP_8fe8ac2c7c0037f5bee7c55b6a976ec1_Traceguids,
      (unsigned int)v14);
  }
  return (unsigned int)v14;
}

```

## disassembly

```asm
0x140039250  mov     [rsp-18h+arg_0], rbx
0x140039255  mov     [rsp-18h+arg_10], rsi
0x14003925a  push    rbp
0x14003925b  push    rdi
0x14003925c  push    r14
0x14003925e  mov     rbp, rsp
0x140039261  sub     rsp, 70h
0x140039265  movups  xmm0, xmmword ptr [rdx]
0x140039268  mov     edi, r9d
0x14003926b  mov     [rbp+arg_8], 0
0x140039272  mov     rsi, r8
0x140039275  mov     [rbp+var_18], 0
0x14003927d  mov     r14, rcx
0x140039280  mov     [rbp+var_20], 0
0x140039288  lea     r9, [rbp+var_20]
0x14003928c  lea     r8, [rbp+var_18]
0x140039290  lea     rdx, [rbp+arg_8]
0x140039294  lea     rcx, [rbp+var_10]
0x140039298  movdqu  [rbp+var_10], xmm0
0x14003929d  call    ?Begin_IdentifyCall_PrvHost@ProviderSubSystem_Globals@@SAJU_tag_WmiInternalContext@@AEAHAEAPEAUIUnknown@@AEAPEAUIServerSecurity@@@Z; ProviderSubSystem_Globals::Begin_IdentifyCall_PrvHost(_tag_WmiInternalContext,int &,IUnknown * &,IServerSecurity * &)
0x1400392a2  mov     ebx, eax
0x1400392a4  test    eax, eax
0x1400392a6  js      short loc_140039306
0x1400392a8  mov     rdx, [rbp+arg_48]
0x1400392ac  lea     rcx, [r14-8]
0x1400392b0  mov     rax, [rcx]
0x1400392b3  mov     r8d, edi
0x1400392b6  mov     r9, [rbp+arg_20]
0x1400392ba  mov     [rsp+70h+var_30], rdx
0x1400392bf  mov     rdx, [rbp+arg_40]
0x1400392c3  mov     rax, [rax+40h]
0x1400392c7  mov     [rsp+70h+var_38], rdx
0x1400392cc  mov     rdx, [rbp+arg_38]
0x1400392d0  mov     [rsp+70h+var_40], rdx
0x1400392d5  mov     rdx, [rbp+arg_30]
0x1400392d9  mov     [rsp+70h+var_48], rdx
0x1400392de  mov     rdx, [rbp+arg_28]
0x1400392e2  mov     [rsp+70h+var_50], rdx
0x1400392e7  mov     rdx, rsi
0x1400392ea  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400392ef  lea     r9, [rbp+arg_8]
0x1400392f3  mov     ebx, eax
0x1400392f5  lea     r8, [rbp+var_20]
0x1400392f9  lea     rdx, [rbp+var_18]
0x1400392fd  call    ?End_IdentifyCall_PrvHost@ProviderSubSystem_Globals@@SAJU_tag_WmiInternalContext@@AEAPEAUIUnknown@@AEAPEAUIServerSecurity@@AEAH@Z; ProviderSubSystem_Globals::End_IdentifyCall_PrvHost(_tag_WmiInternalContext,IUnknown * &,IServerSecurity * &,int &)
0x140039302  test    ebx, ebx
0x140039304  jns     short loc_140039317
0x140039306  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x14003930c  mov     rcx, rax
0x14003930f  mov     edx, ebx
0x140039311  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x140039317  mov     rcx, cs:WPP_GLOBAL_Control
0x14003931e  lea     rax, WPP_GLOBAL_Control
0x140039325  cmp     rcx, rax
0x140039328  jz      short loc_14003934E
0x14003932a  test    byte ptr [rcx+1Ch], 4
0x14003932e  jz      short loc_14003934E
0x140039330  cmp     byte ptr [rcx+19h], 2
0x140039334  jb      short loc_14003934E
0x140039336  mov     rcx, [rcx+10h]
0x14003933a  lea     r8, WPP_8fe8ac2c7c0037f5bee7c55b6a976ec1_Traceguids
0x140039341  mov     edx, 42h ; 'B'
0x140039346  mov     r9d, ebx
0x140039349  call    WPP_SF_d
0x14003934e  lea     r11, [rsp+70h+var_s0]
0x140039353  mov     eax, ebx
0x140039355  mov     rbx, [r11+20h]
0x140039359  mov     rsi, [r11+30h]
0x14003935d  mov     rsp, r11
0x140039360  pop     r14
0x140039362  pop     rdi
0x140039363  pop     rbp
0x140039364  retn
```
