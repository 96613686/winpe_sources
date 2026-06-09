# COleDocObjectItem::OnPrint(CView *,CPrintInfo *,int)

- ea: `0x1800b3390`
- end: `0x1800b35f9`
- name: `?OnPrint@COleDocObjectItem@@SAXPEAVCView@@PEAUCPrintInfo@@H@Z`
- size: `617`
- prototype: `void __fastcall(struct CView *, struct CPrintInfo *, int)`
- caller_count: `0`
- callee_count: `7`
- tags: `service_task, broker_com_uri`

## callees

- `0x18001cd40`
- `0x18008f080`
- `0x180094298`
- `0x1800b3090`
- `0x1800b3390`
- `0x1800b3790`
- `0x1800d7010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800b34ba`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800b34ba`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800b3588`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800b3592`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800b3588`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800b3592`
- `KERNEL32!GlobalUnlock` at `0x1800b35a6`
- `KERNEL32!GlobalUnlock` at `0x1800b35ba`
- `KERNEL32!GlobalUnlock` at `0x1800b35a6`
- `KERNEL32!GlobalUnlock` at `0x1800b35ba`
- `KERNEL32!GlobalLock` at `0x1800b346a`
- `KERNEL32!GlobalLock` at `0x1800b348a`
- `KERNEL32!GlobalLock` at `0x1800b346a`
- `KERNEL32!GlobalLock` at `0x1800b348a`

## pseudocode

```c
void __fastcall COleDocObjectItem::OnPrint(struct CObject **a1, struct CPrintInfo *a2, int a3)
{
  struct CObject *v6; // rax
  COleDocument *v7; // rdi
  struct CDocItem *NextItemOfKind; // r14
  struct CObject *v9; // rsi
  __int64 v10; // rax
  __int64 v11; // rax
  struct tagDEVNAMES *v12; // r14
  struct _devicemodeW *v13; // rax
  _DWORD *v14; // rax
  __int64 v15; // r10
  __int64 v16; // rax
  LPVOID pv; // [rsp+50h] [rbp-20h] BYREF
  LPVOID TargetDevice; // [rsp+58h] [rbp-18h] BYREF
  struct __POSITION *v19; // [rsp+60h] [rbp-10h] BYREF
  int v20; // [rsp+A0h] [rbp+30h] BYREF
  int v21; // [rsp+B8h] [rbp+48h] BYREF

  v6 = AfxDynamicDownCast((struct CRuntimeClass *)&COleDocument::classCOleDocument, a1[16]);
  v7 = v6;
  if ( v6 )
  {
    v19 = (struct __POSITION *)(*(__int64 (__fastcall **)(struct CObject *))(*(_QWORD *)v6 + 376LL))(v6);
    while ( v19 )
    {
      NextItemOfKind = COleDocument::GetNextItemOfKind(
                         v7,
                         &v19,
                         (struct CRuntimeClass *)&COleClientItem::classCOleClientItem);
      v9 = AfxDynamicDownCast((struct CRuntimeClass *)&COleDocObjectItem::classCOleDocObjectItem, NextItemOfKind);
      if ( v9 )
      {
        if ( a3 || (v10 = *((_QWORD *)NextItemOfKind + 19)) != 0 && *(struct CObject **)(v10 + 64) == a1[8] )
        {
          if ( (unsigned int)COleDocObjectItem::SupportsIPrint(v9) )
          {
            v11 = *(_QWORD *)a2;
            TargetDevice = 0;
            v12 = (struct tagDEVNAMES *)GlobalLock(*(HGLOBAL *)(*(_QWORD *)(v11 + 192) + 24LL));
            if ( v12 )
            {
              v13 = (struct _devicemodeW *)GlobalLock(*(HGLOBAL *)(*(_QWORD *)(*(_QWORD *)a2 + 192LL) + 16LL));
              if ( v13 )
              {
                TargetDevice = _AfxOleCreateTargetDevice(v12, v13);
                if ( TargetDevice )
                {
                  v14 = CoTaskMemAlloc(0x18u);
                  pv = v14;
                  if ( v14 )
                  {
                    *v14 = 24;
                    *((_DWORD *)pv + 1) = 1;
                    *((_DWORD *)pv + 2) = 1;
                    *((_DWORD *)pv + 3) = 1;
                    *((_DWORD *)pv + 4) = *(unsigned __int16 *)(*(_QWORD *)(*(_QWORD *)a2 + 192LL) + 44LL);
                    *((_DWORD *)pv + 5) = *(unsigned __int16 *)(*(_QWORD *)(*(_QWORD *)a2 + 192LL) + 46LL);
                    v15 = *((_QWORD *)v9 + 29);
                    v16 = *(_QWORD *)a2;
                    v20 = *((_DWORD *)pv + 4);
                    v21 = 0;
                    (*(void (__fastcall **)(__int64, _QWORD, LPVOID *, LPVOID *, _QWORD, _QWORD, _DWORD, int *, int *))(*(_QWORD *)v15 + 40LL))(
                      v15,
                      2 * (*(_DWORD *)(*(_QWORD *)(v16 + 192) + 40LL) & 0x20 | 4u),
                      &TargetDevice,
                      &pv,
                      0,
                      0,
                      *((_DWORD *)a2 + 6),
                      &v21,
                      &v20);
                    CoTaskMemFree(pv);
                  }
                  CoTaskMemFree(TargetDevice);
                }
                GlobalUnlock(*(HGLOBAL *)(*(_QWORD *)(*(_QWORD *)a2 + 192LL) + 16LL));
              }
              GlobalUnlock(*(HGLOBAL *)(*(_QWORD *)(*(_QWORD *)a2 + 192LL) + 24LL));
            }
          }
          else
          {
            COleDocObjectItem::ExecCommand(v9, 6u, 2u, 0);
          }
        }
      }
    }
  }
}

```

## disassembly

```asm
0x1800b3390  mov     [rsp-28h+arg_8], rbx
0x1800b3395  mov     [rsp-28h+arg_10], rsi
0x1800b339a  push    rbp
0x1800b339b  push    rdi
0x1800b339c  push    r12
0x1800b339e  push    r14
0x1800b33a0  push    r15
0x1800b33a2  mov     rbp, rsp
0x1800b33a5  sub     rsp, 70h
0x1800b33a9  mov     rbx, rdx
0x1800b33ac  mov     r15, rcx
0x1800b33af  mov     rdx, [rcx+80h]; struct CObject *
0x1800b33b6  mov     r12d, r8d
0x1800b33b9  lea     rcx, ?classCOleDocument@COleDocument@@2UCRuntimeClass@@B; struct CRuntimeClass *
0x1800b33c0  call    ?AfxDynamicDownCast@@YAPEAVCObject@@PEAUCRuntimeClass@@PEAV1@@Z; AfxDynamicDownCast(CRuntimeClass *,CObject *)
0x1800b33c5  mov     rdi, rax
0x1800b33c8  test    rax, rax
0x1800b33cb  jz      loc_1800B35E0
0x1800b33d1  mov     r9, [rax]
0x1800b33d4  mov     rcx, rax
0x1800b33d7  mov     rax, [r9+178h]
0x1800b33de  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b33e3  mov     [rbp+var_10], rax
0x1800b33e7  test    rax, rax
0x1800b33ea  jz      loc_1800B35E0
0x1800b33f0  lea     r8, ?classCOleClientItem@COleClientItem@@2UCRuntimeClass@@B; struct CRuntimeClass *
0x1800b33f7  mov     rcx, rdi; this
0x1800b33fa  lea     rdx, [rbp+var_10]; struct __POSITION **
0x1800b33fe  call    ?GetNextItemOfKind@COleDocument@@IEBAPEAVCDocItem@@AEAPEAU__POSITION@@PEAUCRuntimeClass@@@Z; COleDocument::GetNextItemOfKind(__POSITION * &,CRuntimeClass *)
0x1800b3403  mov     rdx, rax; struct CObject *
0x1800b3406  lea     rcx, ?classCOleDocObjectItem@COleDocObjectItem@@2UCRuntimeClass@@B; struct CRuntimeClass *
0x1800b340d  mov     r14, rax
0x1800b3410  call    ?AfxDynamicDownCast@@YAPEAVCObject@@PEAUCRuntimeClass@@PEAV1@@Z; AfxDynamicDownCast(CRuntimeClass *,CObject *)
0x1800b3415  mov     rsi, rax
0x1800b3418  test    rax, rax
0x1800b341b  jz      loc_1800B35D5
0x1800b3421  test    r12d, r12d
0x1800b3424  jnz     short loc_1800B3444
0x1800b3426  mov     rax, [r14+98h]
0x1800b342d  test    rax, rax
0x1800b3430  jz      loc_1800B35D5
0x1800b3436  mov     rcx, [r15+40h]
0x1800b343a  cmp     [rax+40h], rcx
0x1800b343e  jnz     loc_1800B35D5
0x1800b3444  mov     rcx, rsi; this
0x1800b3447  call    ?SupportsIPrint@COleDocObjectItem@@IEAAHXZ; COleDocObjectItem::SupportsIPrint(void)
0x1800b344c  test    eax, eax
0x1800b344e  jz      loc_1800B35C2
0x1800b3454  mov     rax, [rbx]
0x1800b3457  mov     [rbp+var_18], 0
0x1800b345f  mov     rcx, [rax+0C0h]
0x1800b3466  mov     rcx, [rcx+18h]; hMem
0x1800b346a  call    cs:__imp_GlobalLock
0x1800b3470  mov     r14, rax
0x1800b3473  test    rax, rax
0x1800b3476  jz      loc_1800B35D5
0x1800b347c  mov     rcx, [rbx]
0x1800b347f  mov     rcx, [rcx+0C0h]
0x1800b3486  mov     rcx, [rcx+10h]; hMem
0x1800b348a  call    cs:__imp_GlobalLock
0x1800b3490  test    rax, rax
0x1800b3493  jz      loc_1800B35AC
0x1800b3499  mov     rdx, rax; struct _devicemodeW *
0x1800b349c  mov     rcx, r14; struct tagDEVNAMES *
0x1800b349f  call    ?_AfxOleCreateTargetDevice@@YAPEAUtagDVTARGETDEVICE@@PEAUtagDEVNAMES@@PEAU_devicemodeW@@@Z; _AfxOleCreateTargetDevice(tagDEVNAMES *,_devicemodeW *)
0x1800b34a4  mov     [rbp+var_18], rax
0x1800b34a8  test    rax, rax
0x1800b34ab  jz      loc_1800B3598
0x1800b34b1  mov     r14d, 18h
0x1800b34b7  mov     ecx, r14d; cb
0x1800b34ba  call    cs:__imp_CoTaskMemAlloc
0x1800b34c0  mov     [rbp+pv], rax
0x1800b34c4  test    rax, rax
0x1800b34c7  jz      loc_1800B358E
0x1800b34cd  mov     [rax], r14d
0x1800b34d0  lea     ecx, [r14-17h]
0x1800b34d4  mov     rax, [rbp+pv]
0x1800b34d8  lea     r9, [rbp+pv]
0x1800b34dc  mov     [rax+4], ecx
0x1800b34df  mov     rax, [rbp+pv]
0x1800b34e3  mov     [rax+8], ecx
0x1800b34e6  mov     rax, [rbp+pv]
0x1800b34ea  mov     [rax+0Ch], ecx
0x1800b34ed  mov     rax, [rbx]
0x1800b34f0  mov     rcx, [rax+0C0h]
0x1800b34f7  mov     rax, [rbp+pv]
0x1800b34fb  movzx   edx, word ptr [rcx+2Ch]
0x1800b34ff  mov     [rax+10h], edx
0x1800b3502  mov     rax, [rbx]
0x1800b3505  mov     rcx, [rax+0C0h]
0x1800b350c  mov     rax, [rbp+pv]
0x1800b3510  movzx   edx, word ptr [rcx+2Eh]
0x1800b3514  mov     [rax+14h], edx
0x1800b3517  mov     rax, [rbp+pv]
0x1800b351b  mov     r10, [rsi+0E8h]
0x1800b3522  mov     ecx, [rax+10h]
0x1800b3525  mov     rax, [rbx]
0x1800b3528  mov     [rbp+arg_0], ecx
0x1800b352b  mov     [rbp+arg_18], 0
0x1800b3532  mov     r8, [r10]
0x1800b3535  mov     rcx, [rax+0C0h]
0x1800b353c  mov     rax, [r8+28h]
0x1800b3540  mov     edx, [rcx+28h]
0x1800b3543  lea     rcx, [rbp+arg_0]
0x1800b3547  mov     r8d, [rbx+18h]
0x1800b354b  and     edx, 20h
0x1800b354e  mov     [rsp+70h+var_30], rcx
0x1800b3553  or      edx, 4
0x1800b3556  lea     rcx, [rbp+arg_18]
0x1800b355a  add     edx, edx
0x1800b355c  mov     [rsp+70h+var_38], rcx
0x1800b3561  mov     rcx, r10
0x1800b3564  mov     [rsp+70h+var_40], r8d
0x1800b3569  lea     r8, [rbp+var_18]
0x1800b356d  mov     [rsp+70h+var_48], 0
0x1800b3576  mov     [rsp+70h+var_50], 0
0x1800b357f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b3584  mov     rcx, [rbp+pv]; pv
0x1800b3588  call    cs:__imp_CoTaskMemFree
0x1800b358e  mov     rcx, [rbp+var_18]; pv
0x1800b3592  call    cs:__imp_CoTaskMemFree
0x1800b3598  mov     rax, [rbx]
0x1800b359b  mov     rcx, [rax+0C0h]
0x1800b35a2  mov     rcx, [rcx+10h]; hMem
0x1800b35a6  call    cs:__imp_GlobalUnlock
0x1800b35ac  mov     rax, [rbx]
0x1800b35af  mov     rcx, [rax+0C0h]
0x1800b35b6  mov     rcx, [rcx+18h]; hMem
0x1800b35ba  call    cs:__imp_GlobalUnlock
0x1800b35c0  jmp     short loc_1800B35D5
0x1800b35c2  xor     r9d, r9d; struct _GUID *
0x1800b35c5  mov     rcx, rsi; this
0x1800b35c8  lea     edx, [r9+6]; unsigned int
0x1800b35cc  lea     r8d, [r9+2]; unsigned int
0x1800b35d0  call    ?ExecCommand@COleDocObjectItem@@QEAAJKKPEBU_GUID@@@Z; COleDocObjectItem::ExecCommand(ulong,ulong,_GUID const *)
0x1800b35d5  cmp     [rbp+var_10], 0
0x1800b35da  jnz     loc_1800B33F0
0x1800b35e0  lea     r11, [rsp+70h+var_s0]
0x1800b35e5  mov     rbx, [r11+38h]
0x1800b35e9  mov     rsi, [r11+40h]
0x1800b35ed  mov     rsp, r11
0x1800b35f0  pop     r15
0x1800b35f2  pop     r14
0x1800b35f4  pop     r12
0x1800b35f6  pop     rdi
0x1800b35f7  pop     rbp
0x1800b35f8  retn
```
