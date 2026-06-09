# CreateAuthHostWebInstanceThread(IInspectable *,IUnknown *,ulong *,void * *)

- ea: `0x140004e04`
- end: `0x140005100`
- name: `?CreateAuthHostWebInstanceThread@@YAJPEAUIInspectable@@PEAUIUnknown@@PEAKPEAPEAX@Z`
- size: `764`
- prototype: `int(struct IInspectable *, struct IUnknown *, unsigned int *, void **)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x140003210`

## callees

- `0x140002c70`
- `0x140002c98`
- `0x140004e04`
- `0x140014010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x140004fd3`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x140004fd3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140004f66`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140004fe1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140004f66`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140004fe1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400050d6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400050e4`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400050d6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400050e4`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x140004f57`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x140004f57`
- `api-ms-win-core-com-l1-1-0!CoMarshalInterThreadInterfaceInStream` at `0x140004eac`
- `api-ms-win-core-com-l1-1-0!CoMarshalInterThreadInterfaceInStream` at `0x140004f0c`
- `api-ms-win-core-com-l1-1-0!CoMarshalInterThreadInterfaceInStream` at `0x140004eac`
- `api-ms-win-core-com-l1-1-0!CoMarshalInterThreadInterfaceInStream` at `0x140004f0c`
- `api-ms-win-core-synch-l1-2-1!WaitForMultipleObjects` at `0x140005046`
- `api-ms-win-core-synch-l1-2-1!WaitForMultipleObjects` at `0x140005046`

## pseudocode

```c
__int64 __fastcall CreateAuthHostWebInstanceThread(
        struct IInspectable *a1,
        struct IUnknown *a2,
        unsigned int *a3,
        void **a4)
{
  HANDLE v4; // rdi
  struct IInspectableVtbl *lpVtbl; // rax
  HRESULT (__stdcall *QueryInterface)(IInspectable *, const IID *const, void **); // rax
  int v10; // ebx
  _QWORD *v11; // rcx
  __int64 v12; // rdx
  signed int v13; // eax
  signed int LastError; // eax
  DWORD v15; // eax
  DWORD v16; // eax
  HANDLE Handles[2]; // [rsp+30h] [rbp-30h] BYREF
  LPSTREAM ppStm[2]; // [rsp+40h] [rbp-20h] BYREF
  HANDLE hObject[2]; // [rsp+50h] [rbp-10h]
  DWORD ThreadId; // [rsp+90h] [rbp+30h] BYREF
  LPUNKNOWN pUnk; // [rsp+A8h] [rbp+48h] BYREF

  v4 = 0;
  *a4 = 0;
  lpVtbl = a1->lpVtbl;
  ThreadId = 0;
  pUnk = 0;
  QueryInterface = lpVtbl->QueryInterface;
  *(_OWORD *)ppStm = 0;
  *(_OWORD *)hObject = 0;
  *(_OWORD *)Handles = 0;
  v10 = ((__int64 (__fastcall *)(struct IInspectable *, GUID *, LPUNKNOWN *))QueryInterface)(
          a1,
          &GUID_00000000_0000_0000_c000_000000000046,
          &pUnk);
  if ( v10 >= 0 )
  {
    v10 = CoMarshalInterThreadInterfaceInStream(&GUID_af86e2e0_b12d_4c6a_9c5a_d7aa65101e90, pUnk, ppStm);
    ((void (__fastcall *)(LPUNKNOWN))pUnk->lpVtbl->Release)(pUnk);
    pUnk = 0;
    if ( v10 >= 0 )
    {
      v10 = CoMarshalInterThreadInterfaceInStream(&GUID_00000000_0000_0000_c000_000000000046, a2, &ppStm[1]);
      if ( v10 >= 0 )
      {
        hObject[0] = CreateEventW(0, 0, 0, 0);
        if ( hObject[0] )
        {
          LODWORD(hObject[1]) = -2147418113;
          v4 = CreateThread(0, 0, AuthHostWebInstanceThreadProc, ppStm, 0, &ThreadId);
          if ( v4 )
          {
            Handles[0] = hObject[0];
            Handles[1] = v4;
            v15 = WaitForMultipleObjects(2u, Handles, 0, 0xFFFFFFFF);
            v10 = (int)hObject[1];
            if ( v15 )
            {
              if ( SLODWORD(hObject[1]) >= 0 )
              {
                if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                  && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 2) != 0
                  && *((_BYTE *)WPP_GLOBAL_Control + 65) >= 2u )
                {
                  WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 7), 23, &WPP_0796d3d6e744321e50f715e8d649e99c_Traceguids);
                }
                v10 = -2147164127;
              }
            }
            else if ( SLODWORD(hObject[1]) >= 0 )
            {
              v16 = ThreadId;
              *a4 = v4;
              v4 = 0;
              v10 = 0;
              *a3 = v16;
            }
          }
          else
          {
            LastError = GetLastError();
            v10 = LastError;
            if ( LastError > 0 )
              v10 = (unsigned __int16)LastError | 0x80070000;
            v11 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 2) != 0
              && *((_BYTE *)WPP_GLOBAL_Control + 65) >= 2u )
            {
              v12 = 22;
              goto LABEL_6;
            }
          }
        }
        else
        {
          v13 = GetLastError();
          v10 = v13;
          if ( v13 > 0 )
            v10 = (unsigned __int16)v13 | 0x80070000;
          v11 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 2) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 65) >= 2u )
          {
            v12 = 21;
            goto LABEL_6;
          }
        }
      }
      else
      {
        v11 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 2) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 65) >= 2u )
        {
          v12 = 20;
          goto LABEL_6;
        }
      }
    }
    else
    {
      v11 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 2) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 65) >= 2u )
      {
        v12 = 19;
        goto LABEL_6;
      }
    }
  }
  else
  {
    v11 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 2) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 65) >= 2u )
    {
      v12 = 18;
LABEL_6:
      WPP_SF_d(v11[7], v12, &WPP_0796d3d6e744321e50f715e8d649e99c_Traceguids, (unsigned int)v10);
    }
  }
  if ( ppStm[0] )
    (*(void (__fastcall **)(LPSTREAM))(*(_QWORD *)ppStm[0] + 16LL))(ppStm[0]);
  if ( ppStm[1] )
    (*(void (__fastcall **)(LPSTREAM))(*(_QWORD *)ppStm[1] + 16LL))(ppStm[1]);
  if ( hObject[0] )
    CloseHandle(hObject[0]);
  if ( v4 )
    CloseHandle(v4);
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x140004e04  mov     [rsp-28h+arg_8], rbx
0x140004e09  push    rbp
0x140004e0a  push    rsi
0x140004e0b  push    rdi
0x140004e0c  push    r14
0x140004e0e  push    r15
0x140004e10  mov     rbp, rsp
0x140004e13  sub     rsp, 60h
0x140004e17  xorps   xmm0, xmm0
0x140004e1a  xor     edi, edi
0x140004e1c  mov     [r9], rdi
0x140004e1f  mov     r15, r8
0x140004e22  mov     rax, [rcx]
0x140004e25  lea     r8, [rbp+pUnk]
0x140004e29  mov     r14, rdx
0x140004e2c  mov     [rbp+ThreadId], edi
0x140004e2f  lea     rdx, _GUID_00000000_0000_0000_c000_000000000046
0x140004e36  mov     [rbp+pUnk], rdi
0x140004e3a  mov     rsi, r9
0x140004e3d  mov     rax, [rax]
0x140004e40  movups  xmmword ptr [rbp+ppStm], xmm0
0x140004e44  movups  xmmword ptr [rbp+hObject], xmm0
0x140004e48  movups  xmmword ptr [rbp+Handles], xmm0
0x140004e4c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140004e51  mov     ebx, eax
0x140004e53  test    eax, eax
0x140004e55  jns     short loc_140004E9D
0x140004e57  mov     rcx, cs:WPP_GLOBAL_Control
0x140004e5e  lea     rax, WPP_GLOBAL_Control
0x140004e65  cmp     rcx, rax
0x140004e68  jz      loc_1400050A3
0x140004e6e  test    byte ptr [rcx+44h], 2
0x140004e72  jz      loc_1400050A3
0x140004e78  cmp     byte ptr [rcx+41h], 2
0x140004e7c  jb      loc_1400050A3
0x140004e82  lea     edx, [rdi+12h]
0x140004e85  mov     rcx, [rcx+38h]
0x140004e89  lea     r8, WPP_0796d3d6e744321e50f715e8d649e99c_Traceguids
0x140004e90  mov     r9d, ebx
0x140004e93  call    WPP_SF_d
0x140004e98  jmp     loc_1400050A3
0x140004e9d  mov     rdx, [rbp+pUnk]; pUnk
0x140004ea1  lea     r8, [rbp+ppStm]; ppStm
0x140004ea5  lea     rcx, _GUID_af86e2e0_b12d_4c6a_9c5a_d7aa65101e90; riid
0x140004eac  call    cs:__imp_CoMarshalInterThreadInterfaceInStream
0x140004eb2  mov     rcx, [rbp+pUnk]
0x140004eb6  mov     ebx, eax
0x140004eb8  mov     rax, [rcx]
0x140004ebb  mov     rax, [rax+10h]
0x140004ebf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140004ec4  mov     [rbp+pUnk], rdi
0x140004ec8  test    ebx, ebx
0x140004eca  jns     short loc_140004EFE
0x140004ecc  mov     rcx, cs:WPP_GLOBAL_Control
0x140004ed3  lea     rax, WPP_GLOBAL_Control
0x140004eda  cmp     rcx, rax
0x140004edd  jz      loc_1400050A3
0x140004ee3  test    byte ptr [rcx+44h], 2
0x140004ee7  jz      loc_1400050A3
0x140004eed  cmp     byte ptr [rcx+41h], 2
0x140004ef1  jb      loc_1400050A3
0x140004ef7  mov     edx, 13h
0x140004efc  jmp     short loc_140004E85
0x140004efe  lea     r8, [rbp+ppStm+8]; ppStm
0x140004f02  mov     rdx, r14; pUnk
0x140004f05  lea     rcx, _GUID_00000000_0000_0000_c000_000000000046; riid
0x140004f0c  call    cs:__imp_CoMarshalInterThreadInterfaceInStream
0x140004f12  mov     ebx, eax
0x140004f14  test    eax, eax
0x140004f16  jns     short loc_140004F4D
0x140004f18  mov     rcx, cs:WPP_GLOBAL_Control
0x140004f1f  lea     rax, WPP_GLOBAL_Control
0x140004f26  cmp     rcx, rax
0x140004f29  jz      loc_1400050A3
0x140004f2f  test    byte ptr [rcx+44h], 2
0x140004f33  jz      loc_1400050A3
0x140004f39  cmp     byte ptr [rcx+41h], 2
0x140004f3d  jb      loc_1400050A3
0x140004f43  mov     edx, 14h
0x140004f48  jmp     loc_140004E85
0x140004f4d  xor     r9d, r9d; lpName
0x140004f50  xor     r8d, r8d; bInitialState
0x140004f53  xor     edx, edx; bManualReset
0x140004f55  xor     ecx, ecx; lpEventAttributes
0x140004f57  call    cs:__imp_CreateEventW
0x140004f5d  mov     [rbp+hObject], rax
0x140004f61  test    rax, rax
0x140004f64  jnz     short loc_140004FB0
0x140004f66  call    cs:__imp_GetLastError
0x140004f6c  mov     ebx, eax
0x140004f6e  test    eax, eax
0x140004f70  jle     short loc_140004F7B
0x140004f72  movzx   ebx, ax
0x140004f75  or      ebx, 80070000h
0x140004f7b  mov     rcx, cs:WPP_GLOBAL_Control
0x140004f82  lea     rax, WPP_GLOBAL_Control
0x140004f89  cmp     rcx, rax
0x140004f8c  jz      loc_1400050A3
0x140004f92  test    byte ptr [rcx+44h], 2
0x140004f96  jz      loc_1400050A3
0x140004f9c  cmp     byte ptr [rcx+41h], 2
0x140004fa0  jb      loc_1400050A3
0x140004fa6  mov     edx, 15h
0x140004fab  jmp     loc_140004E85
0x140004fb0  lea     rax, [rbp+ThreadId]
0x140004fb4  mov     dword ptr [rbp+hObject+8], 8000FFFFh
0x140004fbb  mov     [rsp+60h+lpThreadId], rax; lpThreadId
0x140004fc0  lea     r9, [rbp+ppStm]; lpParameter
0x140004fc4  lea     r8, _AuthHostWebInstanceThreadProc; lpStartAddress
0x140004fcb  mov     [rsp+60h+dwCreationFlags], edi; dwCreationFlags
0x140004fcf  xor     edx, edx; dwStackSize
0x140004fd1  xor     ecx, ecx; lpThreadAttributes
0x140004fd3  call    cs:__imp_CreateThread
0x140004fd9  mov     rdi, rax
0x140004fdc  test    rax, rax
0x140004fdf  jnz     short loc_14000502B
0x140004fe1  call    cs:__imp_GetLastError
0x140004fe7  mov     ebx, eax
0x140004fe9  test    eax, eax
0x140004feb  jle     short loc_140004FF6
0x140004fed  movzx   ebx, ax
0x140004ff0  or      ebx, 80070000h
0x140004ff6  mov     rcx, cs:WPP_GLOBAL_Control
0x140004ffd  lea     rax, WPP_GLOBAL_Control
0x140005004  cmp     rcx, rax
0x140005007  jz      loc_1400050A3
0x14000500d  test    byte ptr [rcx+44h], 2
0x140005011  jz      loc_1400050A3
0x140005017  cmp     byte ptr [rcx+41h], 2
0x14000501b  jb      loc_1400050A3
0x140005021  mov     edx, 16h
0x140005026  jmp     loc_140004E85
0x14000502b  mov     rax, [rbp+hObject]
0x14000502f  lea     rdx, [rbp+Handles]; lpHandles
0x140005033  xor     r8d, r8d; bWaitAll
0x140005036  mov     [rbp+Handles], rax
0x14000503a  or      r9d, 0FFFFFFFFh; dwMilliseconds
0x14000503e  mov     [rbp+Handles+8], rdi
0x140005042  lea     ecx, [r8+2]; nCount
0x140005046  call    cs:__imp_WaitForMultipleObjects
0x14000504c  mov     ebx, dword ptr [rbp+hObject+8]
0x14000504f  test    eax, eax
0x140005051  jz      short loc_140005092
0x140005053  test    ebx, ebx
0x140005055  js      short loc_1400050A3
0x140005057  mov     rcx, cs:WPP_GLOBAL_Control
0x14000505e  lea     rax, WPP_GLOBAL_Control
0x140005065  cmp     rcx, rax
0x140005068  jz      short loc_14000508B
0x14000506a  test    byte ptr [rcx+44h], 2
0x14000506e  jz      short loc_14000508B
0x140005070  cmp     byte ptr [rcx+41h], 2
0x140005074  jb      short loc_14000508B
0x140005076  mov     rcx, [rcx+38h]
0x14000507a  lea     r8, WPP_0796d3d6e744321e50f715e8d649e99c_Traceguids
0x140005081  mov     edx, 17h
0x140005086  call    WPP_SF_
0x14000508b  mov     ebx, 8004E021h
0x140005090  jmp     short loc_1400050A3
0x140005092  test    ebx, ebx
0x140005094  js      short loc_1400050A3
0x140005096  mov     eax, [rbp+ThreadId]
0x140005099  mov     [rsi], rdi
0x14000509c  xor     edi, edi
0x14000509e  xor     ebx, ebx
0x1400050a0  mov     [r15], eax
0x1400050a3  mov     rcx, [rbp+ppStm]
0x1400050a7  test    rcx, rcx
0x1400050aa  jz      short loc_1400050B8
0x1400050ac  mov     rax, [rcx]
0x1400050af  mov     rax, [rax+10h]
0x1400050b3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400050b8  mov     rcx, [rbp+ppStm+8]
0x1400050bc  test    rcx, rcx
0x1400050bf  jz      short loc_1400050CD
0x1400050c1  mov     rax, [rcx]
0x1400050c4  mov     rax, [rax+10h]
0x1400050c8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400050cd  mov     rcx, [rbp+hObject]; hObject
0x1400050d1  test    rcx, rcx
0x1400050d4  jz      short loc_1400050DC
0x1400050d6  call    cs:__imp_CloseHandle
0x1400050dc  test    rdi, rdi
0x1400050df  jz      short loc_1400050EA
0x1400050e1  mov     rcx, rdi; hObject
0x1400050e4  call    cs:__imp_CloseHandle
0x1400050ea  mov     eax, ebx
0x1400050ec  mov     rbx, [rsp+60h+arg_8]
0x1400050f4  add     rsp, 60h
0x1400050f8  pop     r15
0x1400050fa  pop     r14
0x1400050fc  pop     rdi
0x1400050fd  pop     rsi
0x1400050fe  pop     rbp
0x1400050ff  retn
```
