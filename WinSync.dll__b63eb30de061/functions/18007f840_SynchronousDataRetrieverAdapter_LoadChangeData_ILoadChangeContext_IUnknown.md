# SynchronousDataRetrieverAdapter::LoadChangeData(ILoadChangeContext *,IUnknown * *)

- ea: `0x18007f840`
- end: `0x18007f9be`
- name: `?LoadChangeData@SynchronousDataRetrieverAdapter@@UEAAJPEAUILoadChangeContext@@PEAPEAUIUnknown@@@Z`
- size: `382`
- prototype: `__int64 __fastcall(SynchronousDataRetrieverAdapter *__hidden this, struct ILoadChangeContext *, struct IUnknown **)`
- caller_count: `0`
- callee_count: `4`
- tags: ``

## callees

- `0x18001a038`
- `0x18001ae20`
- `0x18007f840`
- `0x180094010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007f92b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007f92b`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18007f921`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18007f921`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18007f8b6`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18007f8b6`

## pseudocode

```c
__int64 __fastcall SynchronousDataRetrieverAdapter::LoadChangeData(
        SynchronousDataRetrieverAdapter *this,
        struct ILoadChangeContext *a2,
        struct IUnknown **a3)
{
  PVOID *v6; // rcx
  HANDLE EventW; // rax
  signed int v8; // ebx
  signed int LastError; // eax
  int v10; // eax
  struct IUnknown *v11; // rax

  v6 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && *((char *)WPP_GLOBAL_Control + 28) < 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_s(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      14,
      WPP_3c9fbefe89b430fd9fe4fa5a18a79948_Traceguids,
      "SynchronousDataRetrieverAdapter::LoadChangeData");
    v6 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( a2 && a3 )
  {
    EventW = CreateEventW(0, 1, 0, 0);
    *((_QWORD *)this + 7) = EventW;
    if ( EventW )
    {
      v8 = (*(__int64 (__fastcall **)(_QWORD, unsigned __int64))(**((_QWORD **)this + 5) + 32LL))(
             *((_QWORD *)this + 5),
             ((unsigned __int64)this + 8) & -(__int64)(this != 0));
      if ( v8 >= 0 )
      {
        v8 = (*(__int64 (__fastcall **)(_QWORD, struct ILoadChangeContext *))(**((_QWORD **)this + 5) + 48LL))(
               *((_QWORD *)this + 5),
               a2);
        if ( v8 >= 0 && WaitForSingleObject(*((HANDLE *)this + 7), 0xFFFFFFFF) == -1 )
        {
          LastError = GetLastError();
          v8 = LastError;
          if ( LastError > 0 )
            v8 = (unsigned __int16)LastError | 0x80070000;
        }
        v10 = (*(__int64 (__fastcall **)(_QWORD, unsigned __int64))(**((_QWORD **)this + 5) + 40LL))(
                *((_QWORD *)this + 5),
                ((unsigned __int64)this + 8) & -(__int64)(this != 0));
        if ( v8 >= 0 )
        {
          v8 = v10;
          if ( v10 >= 0 )
          {
            v11 = (struct IUnknown *)*((_QWORD *)this + 6);
            *((_QWORD *)this + 6) = 0;
            *a3 = v11;
          }
        }
      }
    }
    else
    {
      v8 = -2147024882;
    }
    v6 = (PVOID *)WPP_GLOBAL_Control;
  }
  else
  {
    v8 = -2147467261;
  }
  if ( v6 != &WPP_GLOBAL_Control && *((char *)v6 + 28) < 0 && *((_BYTE *)v6 + 25) >= 5u )
    WPP_SF_sD(
      (unsigned int)v6[2],
      15,
      (unsigned int)WPP_3c9fbefe89b430fd9fe4fa5a18a79948_Traceguids,
      (unsigned int)"SynchronousDataRetrieverAdapter::LoadChangeData",
      v8);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x18007f840  push    rbx
0x18007f842  push    rbp
0x18007f843  push    rsi
0x18007f844  push    rdi
0x18007f845  push    r14
0x18007f847  push    r15
0x18007f849  sub     rsp, 38h
0x18007f84d  mov     r14, r8
0x18007f850  mov     rsi, rdx
0x18007f853  mov     rdi, rcx
0x18007f856  mov     rcx, cs:WPP_GLOBAL_Control
0x18007f85d  lea     r15, WPP_GLOBAL_Control
0x18007f864  cmp     rcx, r15
0x18007f867  jz      short loc_18007F898
0x18007f869  test    byte ptr [rcx+1Ch], 80h
0x18007f86d  jz      short loc_18007F898
0x18007f86f  cmp     byte ptr [rcx+19h], 5
0x18007f873  jb      short loc_18007F898
0x18007f875  mov     rcx, [rcx+10h]
0x18007f879  lea     r9, aSynchronousdat_1; "SynchronousDataRetrieverAdapter::LoadCh"...
0x18007f880  mov     edx, 0Eh
0x18007f885  lea     r8, WPP_3c9fbefe89b430fd9fe4fa5a18a79948_Traceguids
0x18007f88c  call    WPP_SF_s
0x18007f891  mov     rcx, cs:WPP_GLOBAL_Control
0x18007f898  test    rsi, rsi
0x18007f89b  jz      loc_18007F979
0x18007f8a1  test    r14, r14
0x18007f8a4  jz      loc_18007F979
0x18007f8aa  xor     r9d, r9d; lpName
0x18007f8ad  xor     r8d, r8d; bInitialState
0x18007f8b0  xor     ecx, ecx; lpEventAttributes
0x18007f8b2  lea     edx, [r9+1]; bManualReset
0x18007f8b6  call    cs:__imp_CreateEventW
0x18007f8bc  mov     [rdi+38h], rax
0x18007f8c0  test    rax, rax
0x18007f8c3  jnz     short loc_18007F8D6
0x18007f8c5  mov     ebx, 8007000Eh
0x18007f8ca  mov     rcx, cs:WPP_GLOBAL_Control
0x18007f8d1  jmp     loc_18007F97E
0x18007f8d6  mov     rcx, [rdi+28h]
0x18007f8da  lea     rdx, [rdi+8]
0x18007f8de  mov     rax, rdi
0x18007f8e1  neg     rax
0x18007f8e4  mov     rax, [rcx]
0x18007f8e7  sbb     rbp, rbp
0x18007f8ea  and     rbp, rdx
0x18007f8ed  mov     rdx, rbp
0x18007f8f0  mov     rax, [rax+20h]
0x18007f8f4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007f8f9  mov     ebx, eax
0x18007f8fb  test    eax, eax
0x18007f8fd  js      short loc_18007F8CA
0x18007f8ff  mov     rcx, [rdi+28h]
0x18007f903  mov     rdx, rsi
0x18007f906  mov     rax, [rcx]
0x18007f909  mov     rax, [rax+30h]
0x18007f90d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007f912  mov     ebx, eax
0x18007f914  test    eax, eax
0x18007f916  js      short loc_18007F940
0x18007f918  mov     rcx, [rdi+38h]; hHandle
0x18007f91c  or      esi, 0FFFFFFFFh
0x18007f91f  mov     edx, esi; dwMilliseconds
0x18007f921  call    cs:__imp_WaitForSingleObject
0x18007f927  cmp     eax, esi
0x18007f929  jnz     short loc_18007F940
0x18007f92b  call    cs:__imp_GetLastError
0x18007f931  mov     ebx, eax
0x18007f933  test    eax, eax
0x18007f935  jle     short loc_18007F940
0x18007f937  movzx   ebx, ax
0x18007f93a  or      ebx, 80070000h
0x18007f940  mov     rcx, [rdi+28h]
0x18007f944  mov     rdx, rbp
0x18007f947  mov     rax, [rcx]
0x18007f94a  mov     rax, [rax+28h]
0x18007f94e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007f953  test    ebx, ebx
0x18007f955  js      loc_18007F8CA
0x18007f95b  mov     ebx, eax
0x18007f95d  test    eax, eax
0x18007f95f  js      loc_18007F8CA
0x18007f965  mov     rax, [rdi+30h]
0x18007f969  mov     qword ptr [rdi+30h], 0
0x18007f971  mov     [r14], rax
0x18007f974  jmp     loc_18007F8CA
0x18007f979  mov     ebx, 80004003h
0x18007f97e  cmp     rcx, r15
0x18007f981  jz      short loc_18007F9AF
0x18007f983  test    byte ptr [rcx+1Ch], 80h
0x18007f987  jz      short loc_18007F9AF
0x18007f989  cmp     byte ptr [rcx+19h], 5
0x18007f98d  jb      short loc_18007F9AF
0x18007f98f  mov     rcx, [rcx+10h]
0x18007f993  lea     r9, aSynchronousdat_1; "SynchronousDataRetrieverAdapter::LoadCh"...
0x18007f99a  mov     edx, 0Fh
0x18007f99f  mov     [rsp+68h+var_48], ebx
0x18007f9a3  lea     r8, WPP_3c9fbefe89b430fd9fe4fa5a18a79948_Traceguids
0x18007f9aa  call    WPP_SF_sD
0x18007f9af  mov     eax, ebx
0x18007f9b1  add     rsp, 38h
0x18007f9b5  pop     r15
0x18007f9b7  pop     r14
0x18007f9b9  pop     rdi
0x18007f9ba  pop     rsi
0x18007f9bb  pop     rbp
0x18007f9bc  pop     rbx
0x18007f9bd  retn
```
