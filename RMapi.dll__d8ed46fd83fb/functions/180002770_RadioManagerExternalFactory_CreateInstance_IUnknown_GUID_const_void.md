# RadioManagerExternalFactory::CreateInstance(IUnknown *,_GUID const &,void * *)

- ea: `0x180002770`
- end: `0x1800029da`
- name: `?CreateInstance@RadioManagerExternalFactory@@EEAAJPEAUIUnknown@@AEBU_GUID@@PEAPEAX@Z`
- size: `618`
- prototype: `__int64 __fastcall(RadioManagerExternalFactory *__hidden this, struct IUnknown *, const struct _GUID *, void **)`
- caller_count: `0`
- callee_count: `11`
- tags: `broker_com_uri`

## callees

- `0x180002770`
- `0x180002ec0`
- `0x180003d50`
- `0x18000b07c`
- `0x18001eea8`
- `0x180022e54`
- `0x180022f00`
- `0x180022f0c`
- `0x180022f58`
- `0x180022f70`
- `0x180023088`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800027f0`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180002934`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180002995`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800027f0`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180002934`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180002995`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800027b8`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800027b8`

## pseudocode

```c
__int64 __fastcall RadioManagerExternalFactory::CreateInstance(
        RadioManagerExternalFactory *this,
        struct IUnknown *a2,
        const struct _GUID *a3,
        void **a4)
{
  __int64 v6; // rax
  __int64 v7; // rcx
  int v8; // eax
  unsigned int v9; // edi
  __int64 v10; // rcx
  __int64 v12; // rax
  __int64 v13; // rax
  __int64 v14; // rcx
  void *v15; // rax
  int v16; // eax
  unsigned int v17; // esi
  _BYTE v18[8]; // [rsp+20h] [rbp-28h] BYREF
  struct _RTL_CRITICAL_SECTION *v19; // [rsp+28h] [rbp-20h]

  *a4 = 0;
  if ( a2 )
  {
    if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
      WPP_SF_d(
        *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
        10,
        WPP_ca79b6ae5c6e3755e5d5afc497605ed9_Traceguids,
        2147746064LL);
    return 2147746064LL;
  }
  else
  {
    v6 = *(_QWORD *)&a3->Data1 - *(_QWORD *)&IID_IUIRadioManager.Data1;
    if ( *(_QWORD *)&a3->Data1 == *(_QWORD *)&IID_IUIRadioManager.Data1 )
      v6 = *(_QWORD *)a3->Data4 - *(_QWORD *)IID_IUIRadioManager.Data4;
    if ( v6 )
    {
      v12 = *(_QWORD *)&a3->Data1 - *(_QWORD *)&IID_IUnknown.Data1;
      if ( *(_QWORD *)&a3->Data1 == *(_QWORD *)&IID_IUnknown.Data1 )
        v12 = *(_QWORD *)a3->Data4 - *(_QWORD *)IID_IUnknown.Data4;
      if ( v12 )
      {
        v9 = -2147467263;
        v10 = WPP_GLOBAL_Control;
        if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
          return v9;
        if ( (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) == 0 )
        {
LABEL_9:
          if ( (_UNKNOWN *)v10 != &WPP_GLOBAL_Control && (*(_BYTE *)(v10 + 28) & 4) != 0 )
            WPP_SF_d(*(_QWORD *)(v10 + 16), 15, WPP_ca79b6ae5c6e3755e5d5afc497605ed9_Traceguids, v9);
          return v9;
        }
        WPP_SF_d(
          *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
          14,
          WPP_ca79b6ae5c6e3755e5d5afc497605ed9_Traceguids,
          2147500033LL);
LABEL_8:
        v10 = WPP_GLOBAL_Control;
        goto LABEL_9;
      }
    }
    EnterCriticalSection(&s_singletonRadioManagerLock);
    v19 = &s_singletonRadioManagerLock;
    if ( (unsigned int)Microsoft::WRL::ComPtr<RadioManager>::operator int Microsoft::WRL::Details::BoolStruct::*() != -1 )
    {
LABEL_6:
      v8 = Microsoft::WRL::ComPtr<RadioManager>::CopyTo(v7, a3, a4);
      v9 = v8;
      if ( v8 < 0
        && (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
      {
        WPP_SF_d(
          *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
          13,
          WPP_ca79b6ae5c6e3755e5d5afc497605ed9_Traceguids,
          (unsigned int)v8);
      }
      LeaveCriticalSection(&s_singletonRadioManagerLock);
      goto LABEL_8;
    }
    v13 = Microsoft::WRL::Details::Make<RadioManager,>(v18);
    Microsoft::WRL::ComPtr<RadioManager>::operator=(v14, v13);
    Microsoft::WRL::ComPtr<RadioManager>::~ComPtr<RadioManager>(v18);
    if ( (unsigned int)Microsoft::WRL::ComPtr<RadioManager>::operator int Microsoft::WRL::Details::BoolStruct::*() == -1 )
    {
      if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
        WPP_SF_(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 11, WPP_ca79b6ae5c6e3755e5d5afc497605ed9_Traceguids);
      LeaveCriticalSection(&s_singletonRadioManagerLock);
      return 2147942414LL;
    }
    else
    {
      v15 = (void *)Microsoft::WRL::ComPtr<RadioManager>::operator->();
      v16 = RadioManager::Initialize(v15);
      v17 = v16;
      if ( v16 >= 0 )
        goto LABEL_6;
      if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
        WPP_SF_d(
          *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
          12,
          WPP_ca79b6ae5c6e3755e5d5afc497605ed9_Traceguids,
          (unsigned int)v16);
      Microsoft::WRL::ComPtr<RadioManager>::Reset();
      LeaveCriticalSection(&s_singletonRadioManagerLock);
      return v17;
    }
  }
}

```

## disassembly

```asm
0x180002770  mov     [rsp+arg_0], rbx
0x180002775  push    rbp
0x180002776  push    rsi
0x180002777  push    rdi
0x180002778  sub     rsp, 30h
0x18000277c  mov     rbx, r9
0x18000277f  mov     rdi, r8
0x180002782  mov     qword ptr [r9], 0
0x180002789  test    rdx, rdx
0x18000278c  jnz     loc_18000286D
0x180002792  mov     rax, [r8]
0x180002795  sub     rax, qword ptr cs:IID_IUIRadioManager.Data1
0x18000279c  jnz     short loc_1800027A9
0x18000279e  mov     rax, [r8+8]
0x1800027a2  sub     rax, qword ptr cs:IID_IUIRadioManager.Data4
0x1800027a9  test    rax, rax
0x1800027ac  jnz     short loc_180002815
0x1800027ae  lea     rbp, ?s_singletonRadioManagerLock@@3Vcritical_section@wil@@A; wil::critical_section s_singletonRadioManagerLock
0x1800027b5  mov     rcx, rbp; lpCriticalSection
0x1800027b8  call    cs:__imp_EnterCriticalSection
0x1800027be  mov     [rsp+48h+var_20], rbp
0x1800027c3  call    ??B?$ComPtr@VRadioManager@@@WRL@Microsoft@@QEBAPEQBoolStruct@Details@12@HXZ; Microsoft::WRL::ComPtr<RadioManager>::operator int Microsoft::WRL::Details::BoolStruct::*(void)
0x1800027c8  cmp     eax, 0FFFFFFFFh
0x1800027cb  jz      loc_1800028DC
0x1800027d1  mov     r8, rbx
0x1800027d4  mov     rdx, rdi
0x1800027d7  call    ?CopyTo@?$ComPtr@VRadioManager@@@WRL@Microsoft@@QEBAJAEBU_GUID@@PEAPEAX@Z; Microsoft::WRL::ComPtr<RadioManager>::CopyTo(_GUID const &,void * *)
0x1800027dc  mov     edi, eax
0x1800027de  lea     rbx, WPP_GLOBAL_Control
0x1800027e5  test    eax, eax
0x1800027e7  js      loc_1800029A2
0x1800027ed  mov     rcx, rbp; lpCriticalSection
0x1800027f0  call    cs:__imp_LeaveCriticalSection
0x1800027f6  mov     rcx, cs:WPP_GLOBAL_Control
0x1800027fd  cmp     rcx, rbx
0x180002800  jnz     loc_180002892
0x180002806  mov     eax, edi
0x180002808  mov     rbx, [rsp+48h+arg_0]
0x18000280d  add     rsp, 30h
0x180002811  pop     rdi
0x180002812  pop     rsi
0x180002813  pop     rbp
0x180002814  retn
0x180002815  mov     rax, [r8]
0x180002818  sub     rax, qword ptr cs:IID_IUnknown.Data1
0x18000281f  jnz     short loc_18000282C
0x180002821  mov     rax, [r8+8]
0x180002825  sub     rax, qword ptr cs:IID_IUnknown.Data4
0x18000282c  test    rax, rax
0x18000282f  jz      loc_1800027AE
0x180002835  mov     edi, 80004001h
0x18000283a  lea     rbx, WPP_GLOBAL_Control
0x180002841  mov     rcx, cs:WPP_GLOBAL_Control
0x180002848  cmp     rcx, rbx
0x18000284b  jz      short loc_180002806
0x18000284d  test    byte ptr [rcx+1Ch], 1
0x180002851  jz      short loc_1800027FD
0x180002853  mov     edx, 0Eh
0x180002858  mov     r9d, edi
0x18000285b  lea     r8, WPP_ca79b6ae5c6e3755e5d5afc497605ed9_Traceguids
0x180002862  mov     rcx, [rcx+10h]
0x180002866  call    WPP_SF_d
0x18000286b  jmp     short loc_1800027F6
0x18000286d  lea     rbx, WPP_GLOBAL_Control
0x180002874  mov     rcx, cs:WPP_GLOBAL_Control
0x18000287b  cmp     rcx, rbx
0x18000287e  jnz     short loc_1800028B9
0x180002880  mov     eax, 80040110h
0x180002885  mov     rbx, [rsp+48h+arg_0]
0x18000288a  add     rsp, 30h
0x18000288e  pop     rdi
0x18000288f  pop     rsi
0x180002890  pop     rbp
0x180002891  retn
0x180002892  test    byte ptr [rcx+1Ch], 4
0x180002896  jz      loc_180002806
0x18000289c  mov     edx, 0Fh
0x1800028a1  mov     r9d, edi
0x1800028a4  lea     r8, WPP_ca79b6ae5c6e3755e5d5afc497605ed9_Traceguids
0x1800028ab  mov     rcx, [rcx+10h]
0x1800028af  call    WPP_SF_d
0x1800028b4  jmp     loc_180002806
0x1800028b9  test    byte ptr [rcx+1Ch], 1
0x1800028bd  jz      short loc_180002880
0x1800028bf  mov     edx, 0Ah
0x1800028c4  mov     r9d, 80040110h
0x1800028ca  lea     r8, WPP_ca79b6ae5c6e3755e5d5afc497605ed9_Traceguids
0x1800028d1  mov     rcx, [rcx+10h]
0x1800028d5  call    WPP_SF_d
0x1800028da  jmp     short loc_180002880
0x1800028dc  lea     rcx, [rsp+48h+var_28]
0x1800028e1  call    ??$Make@VRadioManager@@$$V@Details@WRL@Microsoft@@YA?AV?$ComPtr@VRadioManager@@@12@XZ; Microsoft::WRL::Details::Make<RadioManager,>(void)
0x1800028e6  mov     rdx, rax
0x1800028e9  call    ??4?$ComPtr@VRadioManager@@@WRL@Microsoft@@QEAAAEAV012@$$QEAV012@@Z; Microsoft::WRL::ComPtr<RadioManager>::operator=(Microsoft::WRL::ComPtr<RadioManager> &&)
0x1800028ee  lea     rcx, [rsp+48h+var_28]
0x1800028f3  call    ??1?$ComPtr@VRadioManager@@@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::ComPtr<RadioManager>::~ComPtr<RadioManager>(void)
0x1800028f8  call    ??B?$ComPtr@VRadioManager@@@WRL@Microsoft@@QEBAPEQBoolStruct@Details@12@HXZ; Microsoft::WRL::ComPtr<RadioManager>::operator int Microsoft::WRL::Details::BoolStruct::*(void)
0x1800028fd  cmp     eax, 0FFFFFFFFh
0x180002900  jnz     short loc_180002944
0x180002902  lea     rbx, WPP_GLOBAL_Control
0x180002909  mov     rcx, cs:WPP_GLOBAL_Control
0x180002910  cmp     rcx, rbx
0x180002913  jz      short loc_180002931
0x180002915  test    byte ptr [rcx+1Ch], 1
0x180002919  jz      short loc_180002931
0x18000291b  mov     edx, 0Bh
0x180002920  lea     r8, WPP_ca79b6ae5c6e3755e5d5afc497605ed9_Traceguids
0x180002927  mov     rcx, [rcx+10h]
0x18000292b  call    WPP_SF_
0x180002930  nop
0x180002931  mov     rcx, rbp; lpCriticalSection
0x180002934  call    cs:__imp_LeaveCriticalSection
0x18000293a  mov     eax, 8007000Eh
0x18000293f  jmp     loc_180002808
0x180002944  call    ??C?$ComPtr@VRadioManager@@@WRL@Microsoft@@QEBAPEAVRadioManager@@XZ; Microsoft::WRL::ComPtr<RadioManager>::operator->(void)
0x180002949  mov     rcx, rax; pv
0x18000294c  call    ?Initialize@RadioManager@@QEAAJXZ; RadioManager::Initialize(void)
0x180002951  mov     esi, eax
0x180002953  test    eax, eax
0x180002955  jns     loc_1800027D1
0x18000295b  lea     rbx, WPP_GLOBAL_Control
0x180002962  mov     rcx, cs:WPP_GLOBAL_Control
0x180002969  cmp     rcx, rbx
0x18000296c  jz      short loc_18000298C
0x18000296e  test    byte ptr [rcx+1Ch], 1
0x180002972  jz      short loc_18000298C
0x180002974  mov     edx, 0Ch
0x180002979  mov     r9d, eax
0x18000297c  lea     r8, WPP_ca79b6ae5c6e3755e5d5afc497605ed9_Traceguids
0x180002983  mov     rcx, [rcx+10h]
0x180002987  call    WPP_SF_d
0x18000298c  call    ?Reset@?$ComPtr@VRadioManager@@@WRL@Microsoft@@QEAAKXZ; Microsoft::WRL::ComPtr<RadioManager>::Reset(void)
0x180002991  nop
0x180002992  mov     rcx, rbp; lpCriticalSection
0x180002995  call    cs:__imp_LeaveCriticalSection
0x18000299b  mov     eax, esi
0x18000299d  jmp     loc_180002808
0x1800029a2  mov     rcx, cs:WPP_GLOBAL_Control
0x1800029a9  cmp     rcx, rbx
0x1800029ac  jz      loc_1800027ED
0x1800029b2  test    byte ptr [rcx+1Ch], 1
0x1800029b6  jz      loc_1800027ED
0x1800029bc  mov     edx, 0Dh
0x1800029c1  mov     r9d, eax
0x1800029c4  lea     r8, WPP_ca79b6ae5c6e3755e5d5afc497605ed9_Traceguids
0x1800029cb  mov     rcx, [rcx+10h]
0x1800029cf  call    WPP_SF_d
0x1800029d4  jmp     loc_1800027ED
```
