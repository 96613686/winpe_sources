# CHandlerInfo::_GetEventStrings(ISyncMgrEvent *,SYNCMGR_EVENTINFO *)

- ea: `0x18001945c`
- end: `0x180019647`
- name: `?_GetEventStrings@CHandlerInfo@@AEAAJPEAUISyncMgrEvent@@PEAUSYNCMGR_EVENTINFO@@@Z`
- size: `491`
- prototype: `__int64 __fastcall(CHandlerInfo *__hidden this, struct ISyncMgrEvent *, struct SYNCMGR_EVENTINFO *)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x18001906c`

## callees

- `0x180005660`
- `0x18001945c`
- `0x180053010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800194c0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001950e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001955c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800195a4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800195ea`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001962c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800194c0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001950e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001955c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800195a4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800195ea`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001962c`

## pseudocode

```c
__int64 __fastcall CHandlerInfo::_GetEventStrings(
        CHandlerInfo *this,
        struct ISyncMgrEvent *a2,
        struct SYNCMGR_EVENTINFO *a3)
{
  struct ISyncMgrEventVtbl *lpVtbl; // rax
  int v6; // ebx
  struct ISyncMgrEventVtbl *v7; // rax
  struct ISyncMgrEventVtbl *v8; // rax
  struct ISyncMgrEventVtbl *v9; // rax
  struct ISyncMgrEventVtbl *v10; // rax
  struct ISyncMgrEventVtbl *v11; // rax
  LPVOID pv; // [rsp+40h] [rbp+20h] BYREF
  unsigned __int16 *v14; // [rsp+48h] [rbp+28h] BYREF

  pv = this;
  lpVtbl = a2->lpVtbl;
  pv = 0;
  v6 = ((__int64 (__fastcall *)(struct ISyncMgrEvent *, LPVOID *))lpVtbl->GetDescription)(a2, &pv);
  if ( v6 >= 0 )
  {
    v6 = StringCchCopyW((unsigned __int16 *)a3 + 270, 0x104u, (const unsigned __int16 *)pv);
    CoTaskMemFree(pv);
    if ( v6 >= 0 )
    {
      v7 = a2->lpVtbl;
      v14 = 0;
      v6 = ((__int64 (__fastcall *)(struct ISyncMgrEvent *, unsigned __int16 **))v7->GetName)(a2, &v14);
      if ( v6 >= 0 )
      {
        v6 = StringCchCopyW((unsigned __int16 *)a3 + 142, 0x80u, v14);
        CoTaskMemFree(v14);
        if ( v6 >= 0 )
        {
          v8 = a2->lpVtbl;
          v14 = 0;
          v6 = ((__int64 (__fastcall *)(struct ISyncMgrEvent *, unsigned __int16 **))v8->GetItemID)(a2, &v14);
          if ( v6 >= 0 )
          {
            v6 = StringCchCopyW((unsigned __int16 *)a3 + 64, 0x40u, v14);
            CoTaskMemFree(v14);
            if ( v6 >= 0 )
            {
              v9 = a2->lpVtbl;
              v14 = 0;
              if ( ((int (__fastcall *)(struct ISyncMgrEvent *, unsigned __int16 **))v9->GetLinkText)(a2, &v14) < 0
                || (v6 = StringCchCopyW((unsigned __int16 *)a3 + 530, 0x80u, v14), CoTaskMemFree(v14), v6 >= 0) )
              {
                v10 = a2->lpVtbl;
                v14 = 0;
                if ( ((int (__fastcall *)(struct ISyncMgrEvent *, unsigned __int16 **))v10->GetLinkReference)(a2, &v14) < 0
                  || (v6 = StringCchCopyW((unsigned __int16 *)a3 + 658, 0x104u, v14), CoTaskMemFree(v14), v6 >= 0) )
                {
                  v11 = a2->lpVtbl;
                  v14 = 0;
                  if ( ((int (__fastcall *)(struct ISyncMgrEvent *, unsigned __int16 **))v11->GetContext)(a2, &v14) >= 0 )
                  {
                    v6 = StringCchCopyW((unsigned __int16 *)a3 + 918, 0x104u, v14);
                    CoTaskMemFree(v14);
                  }
                }
              }
            }
          }
        }
      }
    }
  }
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x18001945c  mov     [rsp-18h+arg_10], rbx
0x180019461  mov     [rsp-18h+arg_18], rsi
0x180019466  mov     [rsp-18h+pv], rcx
0x18001946b  push    rbp
0x18001946c  push    rdi
0x18001946d  push    r15
0x18001946f  mov     rbp, rsp
0x180019472  sub     rsp, 20h
0x180019476  mov     rax, [rdx]
0x180019479  mov     rdi, rdx
0x18001947c  lea     rdx, [rbp+pv]
0x180019480  mov     [rbp+pv], 0
0x180019488  mov     rcx, rdi
0x18001948b  mov     rsi, r8
0x18001948e  mov     rax, [rax+50h]
0x180019492  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019497  mov     ebx, eax
0x180019499  test    eax, eax
0x18001949b  js      loc_180019632
0x1800194a1  mov     r8, [rbp+pv]; unsigned __int16 *
0x1800194a5  lea     rcx, [rsi+21Ch]; unsigned __int16 *
0x1800194ac  mov     r15d, 104h
0x1800194b2  mov     edx, r15d; unsigned __int64
0x1800194b5  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1800194ba  mov     rcx, [rbp+pv]; pv
0x1800194be  mov     ebx, eax
0x1800194c0  call    cs:__imp_CoTaskMemFree
0x1800194c6  test    ebx, ebx
0x1800194c8  js      loc_180019632
0x1800194ce  mov     rax, [rdi]
0x1800194d1  lea     rdx, [rbp+arg_8]
0x1800194d5  mov     rcx, rdi
0x1800194d8  mov     [rbp+arg_8], 0
0x1800194e0  mov     rax, [rax+48h]
0x1800194e4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800194e9  mov     ebx, eax
0x1800194eb  test    eax, eax
0x1800194ed  js      loc_180019632
0x1800194f3  mov     r8, [rbp+arg_8]; unsigned __int16 *
0x1800194f7  lea     rcx, [rsi+11Ch]; unsigned __int16 *
0x1800194fe  mov     edx, 80h; unsigned __int64
0x180019503  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180019508  mov     rcx, [rbp+arg_8]; pv
0x18001950c  mov     ebx, eax
0x18001950e  call    cs:__imp_CoTaskMemFree
0x180019514  test    ebx, ebx
0x180019516  js      loc_180019632
0x18001951c  mov     rax, [rdi]
0x18001951f  lea     rdx, [rbp+arg_8]
0x180019523  mov     rcx, rdi
0x180019526  mov     [rbp+arg_8], 0
0x18001952e  mov     rax, [rax+28h]
0x180019532  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019537  mov     ebx, eax
0x180019539  test    eax, eax
0x18001953b  js      loc_180019632
0x180019541  mov     r8, [rbp+arg_8]; unsigned __int16 *
0x180019545  lea     rcx, [rsi+80h]; unsigned __int16 *
0x18001954c  mov     edx, 40h ; '@'; unsigned __int64
0x180019551  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180019556  mov     rcx, [rbp+arg_8]; pv
0x18001955a  mov     ebx, eax
0x18001955c  call    cs:__imp_CoTaskMemFree
0x180019562  test    ebx, ebx
0x180019564  js      loc_180019632
0x18001956a  mov     rax, [rdi]
0x18001956d  lea     rdx, [rbp+arg_8]
0x180019571  mov     rcx, rdi
0x180019574  mov     [rbp+arg_8], 0
0x18001957c  mov     rax, [rax+58h]
0x180019580  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019585  test    eax, eax
0x180019587  js      short loc_1800195B2
0x180019589  mov     r8, [rbp+arg_8]; unsigned __int16 *
0x18001958d  lea     rcx, [rsi+424h]; unsigned __int16 *
0x180019594  mov     edx, 80h; unsigned __int64
0x180019599  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18001959e  mov     rcx, [rbp+arg_8]; pv
0x1800195a2  mov     ebx, eax
0x1800195a4  call    cs:__imp_CoTaskMemFree
0x1800195aa  test    ebx, ebx
0x1800195ac  js      loc_180019632
0x1800195b2  mov     rax, [rdi]
0x1800195b5  lea     rdx, [rbp+arg_8]
0x1800195b9  mov     rcx, rdi
0x1800195bc  mov     [rbp+arg_8], 0
0x1800195c4  mov     rax, [rax+60h]
0x1800195c8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800195cd  test    eax, eax
0x1800195cf  js      short loc_1800195F4
0x1800195d1  mov     r8, [rbp+arg_8]; unsigned __int16 *
0x1800195d5  lea     rcx, [rsi+524h]; unsigned __int16 *
0x1800195dc  mov     rdx, r15; unsigned __int64
0x1800195df  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1800195e4  mov     rcx, [rbp+arg_8]; pv
0x1800195e8  mov     ebx, eax
0x1800195ea  call    cs:__imp_CoTaskMemFree
0x1800195f0  test    ebx, ebx
0x1800195f2  js      short loc_180019632
0x1800195f4  mov     rax, [rdi]
0x1800195f7  lea     rdx, [rbp+arg_8]
0x1800195fb  mov     rcx, rdi
0x1800195fe  mov     [rbp+arg_8], 0
0x180019606  mov     rax, [rax+68h]
0x18001960a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001960f  test    eax, eax
0x180019611  js      short loc_180019632
0x180019613  mov     r8, [rbp+arg_8]; unsigned __int16 *
0x180019617  lea     rcx, [rsi+72Ch]; unsigned __int16 *
0x18001961e  mov     rdx, r15; unsigned __int64
0x180019621  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180019626  mov     rcx, [rbp+arg_8]; pv
0x18001962a  mov     ebx, eax
0x18001962c  call    cs:__imp_CoTaskMemFree
0x180019632  mov     rsi, [rsp+20h+arg_18]
0x180019637  mov     eax, ebx
0x180019639  mov     rbx, [rsp+20h+arg_10]
0x18001963e  add     rsp, 20h
0x180019642  pop     r15
0x180019644  pop     rdi
0x180019645  pop     rbp
0x180019646  retn
```
