# PimIMService::UpdateStore(SyncPartnerData const &)

- ea: `0x18000b004`
- end: `0x18000b265`
- name: `?UpdateStore@PimIMService@@AEAAJAEBUSyncPartnerData@@@Z`
- size: `609`
- prototype: `__int64 __fastcall(PimIMService *__hidden this, const struct SyncPartnerData *)`
- caller_count: `1`
- callee_count: `9`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x180006070`

## callees

- `0x180002da8`
- `0x180003468`
- `0x18000428c`
- `0x1800044f0`
- `0x1800045dc`
- `0x18000ab48`
- `0x18000b004`
- `0x180021240`
- `0x180022010`

## string_xrefs

- `0x18000b1a5`: `onecoreuap\base\appmodel\userdataaccess\services\pimindexmaintenance\service\lib\pimimservice.cpp`
- `0x18000b207`: `onecoreuap\base\appmodel\userdataaccess\services\pimindexmaintenance\service\lib\pimimservice.cpp`

## pseudocode

```c
__int64 __fastcall PimIMService::UpdateStore(PimIMService *this, const struct SyncPartnerData *a2, __int64 a3)
{
  __int64 v5; // rcx
  __int64 v6; // rdx
  int v7; // eax
  unsigned int v8; // ebx
  __int64 v9; // r9
  __int64 v10; // rcx
  int i; // ebx
  int updated; // eax
  int v13; // edi
  _BYTE v15[4]; // [rsp+30h] [rbp-29h] BYREF
  _BYTE v16[4]; // [rsp+34h] [rbp-25h] BYREF
  struct IPOutlookFolderCollection *v17; // [rsp+38h] [rbp-21h] BYREF
  int v18; // [rsp+40h] [rbp-19h] BYREF
  __int64 v19; // [rsp+48h] [rbp-11h] BYREF
  __int64 v20; // [rsp+50h] [rbp-9h] BYREF
  int v21; // [rsp+58h] [rbp-1h] BYREF
  __int64 v22; // [rsp+60h] [rbp+7h] BYREF
  int v23; // [rsp+68h] [rbp+Fh]
  struct _EVENT_DATA_DESCRIPTOR v24; // [rsp+70h] [rbp+17h] BYREF

  v20 = 0;
  v19 = 0;
  v17 = 0;
  v22 = 0;
  v23 = 0;
  v21 = 12;
  v18 = 0;
  if ( (Microsoft_Windows_UserDataAccess_PimIndexMaintenanceEnableBits & 0x10) != 0 )
    McGenEventWrite_EventWriteTransfer(
      &MICROSOFT_WINDOWS_USERDATAACCESS_PIMINDEXMAINTENANCE_Context,
      (const EVENT_DESCRIPTOR *)PIMIndex_StoreChangeProcessing_START,
      a3,
      1u,
      &v24);
  v16[1] = 1;
  if ( (Microsoft_Windows_UserDataAccess_PimIndexMaintenanceEnableBits & 0x200) != 0 )
    McGenEventWrite_EventWriteTransfer(
      &MICROSOFT_WINDOWS_USERDATAACCESS_PIMINDEXMAINTENANCE_Context,
      (const EVENT_DESCRIPTOR *)UPDATE_STORE_START,
      a3,
      1u,
      &v24);
  v5 = *(_QWORD *)a2;
  v6 = 0;
  v15[1] = 1;
  if ( v5 )
  {
    if ( (*(int (__fastcall **)(__int64, _QWORD, int *, __int64 *))(*(_QWORD *)v5 + 64LL))(v5, 0, &v21, &v22) >= 0 )
    {
      v7 = (*(__int64 (__fastcall **)(_QWORD, __int64 *, __int64 *))(**((_QWORD **)this + 27) + 112LL))(
             *((_QWORD *)this + 27),
             &v22,
             &v20);
      v8 = v7;
      if ( v7 < 0 )
      {
        v9 = 1514;
LABEL_11:
        v6 = 1;
        v10 = (unsigned int)v7;
        goto LABEL_25;
      }
      v7 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v20 + 120LL))(v20, &v19);
      v8 = v7;
      if ( v7 < 0 )
      {
        v9 = 1517;
        goto LABEL_11;
      }
      v7 = (*(__int64 (__fastcall **)(__int64, wchar_t *, struct IPOutlookFolderCollection **))(*(_QWORD *)v19 + 104LL))(
             v19,
             aDefaultitemtyp,
             &v17);
      v8 = v7;
      if ( v7 < 0 )
      {
        v9 = 1520;
        goto LABEL_11;
      }
      v7 = (*(__int64 (__fastcall **)(struct IPOutlookFolderCollection *, int *))(*(_QWORD *)v17 + 56LL))(v17, &v18);
      v8 = v7;
      if ( v7 < 0 )
      {
        v9 = 1523;
        goto LABEL_11;
      }
      for ( i = 1; i <= v18; ++i )
      {
        updated = PimIMService::UpdateFolder(this, a2, v17, i);
        v13 = updated;
        if ( updated < 0 )
          Log_HREvent(
            (unsigned int)updated,
            0,
            "onecoreuap\\base\\appmodel\\userdataaccess\\services\\pimindexmaintenance\\service\\lib\\pimimservice.cpp",
            1532);
        if ( v13 == -2147023781 )
        {
          v8 = -2147023781;
          goto LABEL_26;
        }
      }
    }
    tlx::_UndoSolo__lambda_8c895a9a157448337de011d0e6f887ca___::__UndoSolo__lambda_8c895a9a157448337de011d0e6f887ca___(v15);
    tlx::_UndoSolo__lambda_70e3843f39a4622e5ca3808dddc41a8c___::__UndoSolo__lambda_70e3843f39a4622e5ca3808dddc41a8c___(v16);
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((__int64 *)&v17);
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v19);
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v20);
    return 0;
  }
  v8 = -2147467259;
  v9 = 1504;
  v10 = 2147500037LL;
LABEL_25:
  Log_HREvent(
    v10,
    v6,
    "onecoreuap\\base\\appmodel\\userdataaccess\\services\\pimindexmaintenance\\service\\lib\\pimimservice.cpp",
    v9);
LABEL_26:
  tlx::_UndoSolo__lambda_8c895a9a157448337de011d0e6f887ca___::__UndoSolo__lambda_8c895a9a157448337de011d0e6f887ca___(v15);
  tlx::_UndoSolo__lambda_70e3843f39a4622e5ca3808dddc41a8c___::__UndoSolo__lambda_70e3843f39a4622e5ca3808dddc41a8c___(v16);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((__int64 *)&v17);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v19);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v20);
  return v8;
}

```

## disassembly

```asm
0x18000b004  mov     [rsp-8+arg_10], rbx
0x18000b009  push    rbp
0x18000b00a  push    rsi
0x18000b00b  push    rdi
0x18000b00c  push    r14
0x18000b00e  push    r15
0x18000b010  lea     rbp, [rsp-37h]
0x18000b015  sub     rsp, 90h
0x18000b01c  mov     rax, cs:__security_cookie
0x18000b023  xor     rax, rsp
0x18000b026  mov     [rbp+57h+var_30], rax
0x18000b02a  xor     eax, eax
0x18000b02c  mov     [rbp+57h+var_60], 0
0x18000b034  test    byte ptr cs:Microsoft_Windows_UserDataAccess_PimIndexMaintenanceEnableBits, 10h
0x18000b03b  mov     rsi, rdx
0x18000b03e  mov     r14, rcx
0x18000b041  mov     [rbp+57h+var_68], 0
0x18000b049  mov     [rbp+57h+var_78], 0
0x18000b051  lea     r15d, [rax+1]
0x18000b055  mov     [rbp+57h+var_50], rax
0x18000b059  mov     [rbp+57h+var_48], eax
0x18000b05c  mov     [rbp+57h+var_58], 0Ch
0x18000b063  mov     [rbp+57h+var_70], eax
0x18000b066  jz      short loc_18000B087
0x18000b068  lea     rax, [rbp+57h+var_40]
0x18000b06c  mov     r9d, r15d
0x18000b06f  lea     rdx, PIMIndex_StoreChangeProcessing_START
0x18000b076  mov     [rsp+0B0h+var_90], rax
0x18000b07b  lea     rcx, MICROSOFT_WINDOWS_USERDATAACCESS_PIMINDEXMAINTENANCE_Context
0x18000b082  call    McGenEventWrite_EventWriteTransfer
0x18000b087  test    byte ptr cs:Microsoft_Windows_UserDataAccess_PimIndexMaintenanceEnableBits+1, 2
0x18000b08e  mov     [rbp+57h+var_7B], r15b
0x18000b092  jz      short loc_18000B0B3
0x18000b094  lea     rax, [rbp+57h+var_40]
0x18000b098  mov     r9d, r15d
0x18000b09b  lea     rdx, UPDATE_STORE_START
0x18000b0a2  mov     [rsp+0B0h+var_90], rax
0x18000b0a7  lea     rcx, MICROSOFT_WINDOWS_USERDATAACCESS_PIMINDEXMAINTENANCE_Context
0x18000b0ae  call    McGenEventWrite_EventWriteTransfer
0x18000b0b3  mov     rcx, [rsi]
0x18000b0b6  xor     edx, edx
0x18000b0b8  mov     [rbp+57h+var_7F], r15b
0x18000b0bc  test    rcx, rcx
0x18000b0bf  jz      loc_18000B1FA
0x18000b0c5  mov     rax, [rcx]
0x18000b0c8  lea     r9, [rbp+57h+var_50]
0x18000b0cc  lea     r8, [rbp+57h+var_58]
0x18000b0d0  mov     rax, [rax+40h]
0x18000b0d4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b0d9  test    eax, eax
0x18000b0db  js      loc_18000B1C9
0x18000b0e1  mov     rcx, [r14+0D8h]
0x18000b0e8  lea     r8, [rbp+57h+var_60]
0x18000b0ec  lea     rdx, [rbp+57h+var_50]
0x18000b0f0  mov     rax, [rcx]
0x18000b0f3  mov     rax, [rax+70h]
0x18000b0f7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b0fc  mov     ebx, eax
0x18000b0fe  test    eax, eax
0x18000b100  jns     short loc_18000B10A
0x18000b102  mov     r9d, 5EAh
0x18000b108  jmp     short loc_18000B12A
0x18000b10a  mov     rcx, [rbp+57h+var_60]
0x18000b10e  lea     rdx, [rbp+57h+var_68]
0x18000b112  mov     rax, [rcx]
0x18000b115  mov     rax, [rax+78h]
0x18000b119  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b11e  mov     ebx, eax
0x18000b120  test    eax, eax
0x18000b122  jns     short loc_18000B134
0x18000b124  mov     r9d, 5EDh
0x18000b12a  mov     edx, r15d
0x18000b12d  mov     ecx, eax
0x18000b12f  jmp     loc_18000B207
0x18000b134  mov     rcx, [rbp+57h+var_68]
0x18000b138  lea     r8, [rbp+57h+var_78]
0x18000b13c  lea     rdx, aDefaultitemtyp; "[DefaultItemType]=2"
0x18000b143  mov     rax, [rcx]
0x18000b146  mov     rax, [rax+68h]
0x18000b14a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b14f  mov     ebx, eax
0x18000b151  test    eax, eax
0x18000b153  jns     short loc_18000B15D
0x18000b155  mov     r9d, 5F0h
0x18000b15b  jmp     short loc_18000B12A
0x18000b15d  mov     rcx, [rbp+57h+var_78]
0x18000b161  lea     rdx, [rbp+57h+var_70]
0x18000b165  mov     rax, [rcx]
0x18000b168  mov     rax, [rax+38h]
0x18000b16c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b171  mov     ebx, eax
0x18000b173  test    eax, eax
0x18000b175  jns     short loc_18000B17F
0x18000b177  mov     r9d, 5F3h
0x18000b17d  jmp     short loc_18000B12A
0x18000b17f  mov     ebx, r15d
0x18000b182  cmp     ebx, [rbp+57h+var_70]
0x18000b185  jg      short loc_18000B1C9
0x18000b187  mov     r8, [rbp+57h+var_78]; struct IPOutlookFolderCollection *
0x18000b18b  mov     r9d, ebx; int
0x18000b18e  mov     rdx, rsi; struct SyncPartnerData *
0x18000b191  mov     rcx, r14; this
0x18000b194  call    ?UpdateFolder@PimIMService@@AEAAJAEBUSyncPartnerData@@PEAUIPOutlookFolderCollection@@H@Z; PimIMService::UpdateFolder(SyncPartnerData const &,IPOutlookFolderCollection *,int)
0x18000b199  mov     edi, eax
0x18000b19b  test    eax, eax
0x18000b19d  jns     short loc_18000B1B5
0x18000b19f  mov     r9d, 5FCh
0x18000b1a5  lea     r8, aOnecoreuapBase_0; "onecoreuap\\base\\appmodel\\userdataacc"...
0x18000b1ac  xor     edx, edx
0x18000b1ae  mov     ecx, eax
0x18000b1b0  call    Log_HREvent
0x18000b1b5  cmp     edi, 8007045Bh
0x18000b1bb  jz      short loc_18000B1C2
0x18000b1bd  add     ebx, r15d
0x18000b1c0  jmp     short loc_18000B182
0x18000b1c2  mov     ebx, 8007045Bh
0x18000b1c7  jmp     short loc_18000B213
0x18000b1c9  lea     rcx, [rbp+57h+var_80]
0x18000b1cd  call    tlx___UndoSolo__lambda_8c895a9a157448337de011d0e6f887ca_______UndoSolo__lambda_8c895a9a157448337de011d0e6f887ca___
0x18000b1d2  lea     rcx, [rbp+57h+var_7C]
0x18000b1d6  call    tlx___UndoSolo__lambda_70e3843f39a4622e5ca3808dddc41a8c_______UndoSolo__lambda_70e3843f39a4622e5ca3808dddc41a8c___
0x18000b1db  lea     rcx, [rbp+57h+var_78]
0x18000b1df  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18000b1e4  lea     rcx, [rbp+57h+var_68]
0x18000b1e8  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18000b1ed  lea     rcx, [rbp+57h+var_60]
0x18000b1f1  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18000b1f6  xor     eax, eax
0x18000b1f8  jmp     short loc_18000B242
0x18000b1fa  mov     ebx, 80004005h
0x18000b1ff  mov     r9d, 5E0h
0x18000b205  mov     ecx, ebx
0x18000b207  lea     r8, aOnecoreuapBase_0; "onecoreuap\\base\\appmodel\\userdataacc"...
0x18000b20e  call    Log_HREvent
0x18000b213  lea     rcx, [rbp+57h+var_80]
0x18000b217  call    tlx___UndoSolo__lambda_8c895a9a157448337de011d0e6f887ca_______UndoSolo__lambda_8c895a9a157448337de011d0e6f887ca___
0x18000b21c  lea     rcx, [rbp+57h+var_7C]
0x18000b220  call    tlx___UndoSolo__lambda_70e3843f39a4622e5ca3808dddc41a8c_______UndoSolo__lambda_70e3843f39a4622e5ca3808dddc41a8c___
0x18000b225  lea     rcx, [rbp+57h+var_78]
0x18000b229  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18000b22e  lea     rcx, [rbp+57h+var_68]
0x18000b232  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18000b237  lea     rcx, [rbp+57h+var_60]
0x18000b23b  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18000b240  mov     eax, ebx
0x18000b242  mov     rcx, [rbp+57h+var_30]
0x18000b246  xor     rcx, rsp; StackCookie
0x18000b249  call    __security_check_cookie
0x18000b24e  mov     rbx, [rsp+0B0h+arg_10]
0x18000b256  add     rsp, 90h
0x18000b25d  pop     r15
0x18000b25f  pop     r14
0x18000b261  pop     rdi
0x18000b262  pop     rsi
0x18000b263  pop     rbp
0x18000b264  retn
```
