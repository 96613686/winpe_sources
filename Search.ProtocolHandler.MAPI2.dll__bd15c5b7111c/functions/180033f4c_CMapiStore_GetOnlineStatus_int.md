# CMapiStore::GetOnlineStatus(int *)

- ea: `0x180033f4c`
- end: `0x1800340ba`
- name: `?GetOnlineStatus@CMapiStore@@AEAAJPEAH@Z`
- size: `366`
- prototype: `__int64 __fastcall(CMapiStore *__hidden this, int *)`
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x180032328`

## callees

- `0x18000ad14`
- `0x1800113ac`
- `0x1800113ec`
- `0x180033f4c`
- `0x1800340c0`
- `0x180034370`
- `0x18003f010`

## string_xrefs

- `0x180033ff3`: `Checking OST status with HrOpenOfflineObj: Online`
- `0x18003400c`: `Checking OST status with HrOpenOfflineObj: Offline`
- `0x180034020`: `Checking OST status with HrOpenOfflineObj: No result returned`
- `0x180034033`: `Checking OST status with HrOpenOfflineObj failed`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CMapiStore::GetOnlineStatus(CMapiStore *this, int *a2)
{
  __int64 v4; // rax
  __int64 (__fastcall *v5)(_QWORD, _QWORD, GUID *, _QWORD, __int64 *); // rax
  int v6; // ebp
  int v7; // ebx
  int v8; // eax
  int RootFolderorIPMSubTree; // eax
  struct IMAPIFolder *v11; // [rsp+50h] [rbp+8h] BYREF
  __int64 v12; // [rsp+58h] [rbp+10h] BYREF

  *a2 = 0;
  if ( *((_QWORD *)this + 6) && *((_DWORD *)this + 28) )
  {
    v4 = *((_QWORD *)this + 78);
    if ( !v4 )
      goto LABEL_17;
    v5 = *(__int64 (__fastcall **)(_QWORD, _QWORD, GUID *, _QWORD, __int64 *))(v4 + 248);
    if ( v5 )
    {
      v6 = 0;
      v12 = 0;
      v7 = v5(0, *((_QWORD *)this + 83), &GUID_GlobalState, 0, &v12);
      if ( v7 < 0
        || (LODWORD(v11) = 0,
            v7 = (*(__int64 (__fastcall **)(__int64, struct IMAPIFolder **))(*(_QWORD *)v12 + 40LL))(v12, &v11),
            v7 < 0) )
      {
        CLogger::Info(v7, L"Checking OST status with HrOpenOfflineObj failed");
      }
      else
      {
        v8 = (unsigned __int8)v11 & 3;
        if ( v8 == 2 )
        {
          CLogger::Info(L"Checking OST status with HrOpenOfflineObj: Online");
          *a2 = 1;
        }
        else if ( v8 == 1 )
        {
          CLogger::Info(L"Checking OST status with HrOpenOfflineObj: Offline");
          *a2 = 0;
        }
        else
        {
          CLogger::Info(L"Checking OST status with HrOpenOfflineObj: No result returned");
          v6 = 1;
        }
      }
      ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v12);
    }
    else
    {
      v7 = 0;
      v6 = 1;
    }
    if ( v7 >= 0 && v6 )
    {
LABEL_17:
      v11 = 0;
      RootFolderorIPMSubTree = CMapiStore::GetRootFolderorIPMSubTree(this, &v11, 0);
      v7 = RootFolderorIPMSubTree;
      if ( RootFolderorIPMSubTree < 0 )
        CLogger::Info(RootFolderorIPMSubTree, L"Checking OST status with ICS failed");
      else
        *a2 = CMapiStore::IsICSSupported(this, v11);
      ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((__int64 *)&v11);
    }
  }
  else
  {
    return (unsigned int)-2147467259;
  }
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x180033f4c  mov     r11, rsp
0x180033f4f  mov     [r11+18h], rbx
0x180033f53  push    rbp
0x180033f54  push    rsi
0x180033f55  push    rdi
0x180033f56  sub     rsp, 30h
0x180033f5a  mov     rsi, rdx
0x180033f5d  mov     rdi, rcx
0x180033f60  mov     dword ptr [rdx], 0
0x180033f66  cmp     qword ptr [rcx+30h], 0
0x180033f6b  jz      loc_1800340A6
0x180033f71  cmp     dword ptr [rcx+70h], 0
0x180033f75  jz      loc_1800340A6
0x180033f7b  mov     rax, [rcx+270h]
0x180033f82  test    rax, rax
0x180033f85  jz      loc_18003405B
0x180033f8b  mov     rax, [rax+0F8h]
0x180033f92  test    rax, rax
0x180033f95  jz      loc_18003404E
0x180033f9b  xor     ebp, ebp
0x180033f9d  mov     [r11+10h], rbp
0x180033fa1  lea     rcx, [r11+10h]
0x180033fa5  mov     [r11-28h], rcx
0x180033fa9  xor     r9d, r9d
0x180033fac  lea     r8, GUID_GlobalState
0x180033fb3  mov     rdx, [rdi+298h]
0x180033fba  xor     ecx, ecx
0x180033fbc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180033fc1  mov     ebx, eax
0x180033fc3  test    eax, eax
0x180033fc5  js      short loc_180034033
0x180033fc7  mov     dword ptr [rsp+48h+arg_0], ebp
0x180033fcb  mov     rcx, [rsp+48h+arg_8]
0x180033fd0  mov     rax, [rcx]
0x180033fd3  lea     rdx, [rsp+48h+arg_0]
0x180033fd8  mov     rax, [rax+28h]
0x180033fdc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180033fe1  mov     ebx, eax
0x180033fe3  test    eax, eax
0x180033fe5  js      short loc_180034033
0x180033fe7  mov     eax, dword ptr [rsp+48h+arg_0]
0x180033feb  and     eax, 3
0x180033fee  cmp     eax, 2
0x180033ff1  jnz     short loc_180034007
0x180033ff3  lea     rcx, aCheckingOstSta; "Checking OST status with HrOpenOfflineO"...
0x180033ffa  call    ?Info@CLogger@@SAXPEB_WZZ; CLogger::Info(wchar_t const *,...)
0x180033fff  mov     dword ptr [rsi], 1
0x180034005  jmp     short loc_180034042
0x180034007  cmp     eax, 1
0x18003400a  jnz     short loc_180034020
0x18003400c  lea     rcx, aCheckingOstSta_2; "Checking OST status with HrOpenOfflineO"...
0x180034013  call    ?Info@CLogger@@SAXPEB_WZZ; CLogger::Info(wchar_t const *,...)
0x180034018  mov     dword ptr [rsi], 0
0x18003401e  jmp     short loc_180034042
0x180034020  lea     rcx, aCheckingOstSta_0; "Checking OST status with HrOpenOfflineO"...
0x180034027  call    ?Info@CLogger@@SAXPEB_WZZ; CLogger::Info(wchar_t const *,...)
0x18003402c  mov     ebp, 1
0x180034031  jmp     short loc_180034042
0x180034033  lea     rdx, aCheckingOstSta_1; "Checking OST status with HrOpenOfflineO"...
0x18003403a  mov     ecx, ebx; int
0x18003403c  call    ?Info@CLogger@@SAXJPEB_WZZ; CLogger::Info(long,wchar_t const *,...)
0x180034041  nop
0x180034042  lea     rcx, [rsp+48h+arg_8]
0x180034047  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18003404c  jmp     short loc_180034053
0x18003404e  xor     ebx, ebx
0x180034050  lea     ebp, [rbx+1]
0x180034053  test    ebx, ebx
0x180034055  js      short loc_1800340AB
0x180034057  test    ebp, ebp
0x180034059  jz      short loc_1800340AB
0x18003405b  mov     [rsp+48h+arg_0], 0
0x180034064  xor     r8d, r8d; int
0x180034067  lea     rdx, [rsp+48h+arg_0]; struct IMAPIFolder **
0x18003406c  mov     rcx, rdi; this
0x18003406f  call    ?GetRootFolderorIPMSubTree@CMapiStore@@QEAAJPEAPEAUIMAPIFolder@@H@Z; CMapiStore::GetRootFolderorIPMSubTree(IMAPIFolder * *,int)
0x180034074  mov     ebx, eax
0x180034076  test    eax, eax
0x180034078  js      short loc_18003408B
0x18003407a  mov     rdx, [rsp+48h+arg_0]; struct IMAPIFolder *
0x18003407f  mov     rcx, rdi; this
0x180034082  call    ?IsICSSupported@CMapiStore@@AEAAHPEAUIMAPIFolder@@@Z; CMapiStore::IsICSSupported(IMAPIFolder *)
0x180034087  mov     [rsi], eax
0x180034089  jmp     short loc_18003409A
0x18003408b  lea     rdx, aCheckingOstSta_3; "Checking OST status with ICS failed"
0x180034092  mov     ecx, eax; int
0x180034094  call    ?Info@CLogger@@SAXJPEB_WZZ; CLogger::Info(long,wchar_t const *,...)
0x180034099  nop
0x18003409a  lea     rcx, [rsp+48h+arg_0]
0x18003409f  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x1800340a4  jmp     short loc_1800340AB
0x1800340a6  mov     ebx, 80004005h
0x1800340ab  mov     eax, ebx
0x1800340ad  mov     rbx, [rsp+48h+arg_10]
0x1800340b2  add     rsp, 30h
0x1800340b6  pop     rdi
0x1800340b7  pop     rsi
0x1800340b8  pop     rbp
0x1800340b9  retn
```
