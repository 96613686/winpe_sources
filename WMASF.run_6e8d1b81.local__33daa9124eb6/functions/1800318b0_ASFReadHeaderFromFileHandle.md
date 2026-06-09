# ASFReadHeaderFromFileHandle

- ea: `0x1800318b0`
- end: `0x180031c99`
- name: `ASFReadHeaderFromFileHandle`
- size: `1001`
- prototype: `__int64 __fastcall(HANDLE hFile, _QWORD *)`
- caller_count: `0`
- callee_count: `9`
- tags: `file_ops`

## callees

- `0x1800011c0`
- `0x1800011cc`
- `0x1800015d0`
- `0x1800021dc`
- `0x18000220c`
- `0x180030960`
- `0x1800318b0`
- `0x18003f2a0`
- `0x180040010`

## import_xrefs

- `KERNEL32!ReadFile` at `0x180031a4b`
- `KERNEL32!ReadFile` at `0x180031a4b`
- `KERNEL32!SetFilePointer` at `0x1800319d7`
- `KERNEL32!SetFilePointer` at `0x1800319d7`

## pseudocode

```c
__int64 __fastcall ASFReadHeaderFromFileHandle(HANDLE hFile, _QWORD *a2)
{
  char *v5; // rdi
  int i; // ebx
  unsigned int v7; // esi
  char *v8; // rax
  char *v9; // r14
  __int64 v10; // rcx
  char v11[8]; // [rsp+30h] [rbp-39h] BYREF
  unsigned __int64 v12; // [rsp+38h] [rbp-31h] BYREF
  __int64 v13; // [rsp+40h] [rbp-29h] BYREF
  __int64 v14; // [rsp+48h] [rbp-21h] BYREF
  __int64 v15; // [rsp+50h] [rbp-19h] BYREF
  __int64 v16; // [rsp+58h] [rbp-11h] BYREF
  struct IWMSCriticalSection *v17; // [rsp+60h] [rbp-9h] BYREF
  DWORD NumberOfBytesRead; // [rsp+68h] [rbp-1h] BYREF
  __int64 v19; // [rsp+70h] [rbp+7h] BYREF
  __int128 v20; // [rsp+78h] [rbp+Fh] BYREF

  if ( hFile == (HANDLE)-1LL )
    return 2147500037LL;
  *a2 = 0;
  v5 = 0;
  v13 = 0;
  v15 = 0;
  i = ASFCreateLibrary(&v13);
  if ( i >= 0 )
  {
    v16 = 0;
    i = (**(__int64 (__fastcall ***)(__int64, GUID *, __int64 *))v13)(v13, &IID_IASFLibraryPriv, &v16);
    if ( i >= 0 )
    {
      v17 = 0;
      i = (*(__int64 (__fastcall **)(__int64, struct IWMSCriticalSection **))(*(_QWORD *)v16 + 24LL))(v16, &v17);
      if ( v16 )
      {
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v16 + 16LL))(v16);
        v16 = 0;
      }
      if ( i >= 0 )
      {
        CAutoCritSec::CAutoCritSec((CAutoCritSec *)v11, v17);
        if ( v17 )
        {
          (*(void (__fastcall **)(struct IWMSCriticalSection *))(*(_QWORD *)v17 + 16LL))(v17);
          v17 = 0;
        }
        LODWORD(v12) = 0;
        if ( (*(int (__fastcall **)(__int64, unsigned __int64 *))(*(_QWORD *)v13 + 40LL))(v13, &v12) >= 0 )
        {
          if ( SetFilePointer(hFile, 0, 0, 0) != -1 )
          {
            v7 = 0;
LABEL_16:
            for ( i = -1072887855;
                  i == -1072887855;
                  i = (*(__int64 (__fastcall **)(__int64, _QWORD, char *, unsigned __int64 *))(*(_QWORD *)v15 + 64LL))(
                        v15,
                        v7,
                        v9,
                        &v12) )
            {
              v8 = (char *)operator new[]((unsigned int)v12);
              v9 = v8;
              if ( !v8 )
              {
                i = -2147024882;
                goto LABEL_39;
              }
              if ( v5 )
              {
                memcpy_0(v8, v5, v7);
                operator delete(v5);
              }
              NumberOfBytesRead = 0;
              v5 = v9;
              if ( !ReadFile(hFile, &v9[v7], v12 - v7, &NumberOfBytesRead, 0)
                || NumberOfBytesRead < (unsigned int)v12 - v7 )
              {
                i = -1072887838;
                goto LABEL_39;
              }
              v7 = v12;
              v19 = 0;
              v20 = 0;
              i = (*(__int64 (__fastcall **)(__int64, _QWORD, char *, __int128 *, __int64 *))(*(_QWORD *)v13 + 48LL))(
                    v13,
                    (unsigned int)v12,
                    v9,
                    &v20,
                    &v19);
              if ( i < 0 )
                goto LABEL_39;
              if ( v7 < (unsigned int)v19 )
              {
                LODWORD(v12) = v19;
                goto LABEL_16;
              }
              i = (*(__int64 (__fastcall **)(__int64, __int128 *, __int64 *))(*(_QWORD *)v13 + 56LL))(v13, &v20, &v15);
              if ( i < 0 )
                goto LABEL_39;
              v14 = 0;
              i = (**(__int64 (__fastcall ***)(__int64, GUID *, __int64 *))v13)(v13, &IID_IASFUnknownContainer, &v14);
              if ( i < 0 )
                goto LABEL_39;
              i = (*(__int64 (__fastcall **)(__int64, GUID *, __int64, __int64))(*(_QWORD *)v14 + 40LL))(
                    v14,
                    &GUID_NULL,
                    v15,
                    0xFFFFFFFFLL);
              if ( v14 )
              {
                (*(void (__fastcall **)(__int64))(*(_QWORD *)v14 + 16LL))(v14);
                v14 = 0;
              }
              if ( i < 0 )
                goto LABEL_39;
            }
            if ( i >= 0 )
            {
              i = (**(__int64 (__fastcall ***)(__int64, GUID *, _QWORD *))v15)(v15, &IID_IASFHeaderObject, a2);
              if ( i < 0 )
                goto LABEL_12;
              v14 = 0;
              i = (**(__int64 (__fastcall ***)(__int64, GUID *, __int64 *))v13)(v13, &IID_IASFUnknownContainer, &v14);
              if ( i < 0 )
                goto LABEL_12;
              i = (*(__int64 (__fastcall **)(__int64, GUID *, __int64, __int64))(*(_QWORD *)v14 + 40LL))(
                    v14,
                    &GUID_NULL,
                    v15,
                    0xFFFFFFFFLL);
              if ( v14 )
              {
                (*(void (__fastcall **)(__int64))(*(_QWORD *)v14 + 16LL))(v14);
                v14 = 0;
              }
            }
LABEL_39:
            CAutoCritSec::~CAutoCritSec((CAutoCritSec *)v11);
            if ( i >= 0 )
              goto LABEL_42;
            goto LABEL_40;
          }
          i = -2147467259;
        }
        else
        {
          i = -2147418113;
        }
LABEL_12:
        CAutoCritSec::~CAutoCritSec((CAutoCritSec *)v11);
      }
    }
  }
LABEL_40:
  if ( *a2 )
  {
    (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*a2 + 16LL))(*a2);
    *a2 = 0;
  }
LABEL_42:
  if ( v15 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v15 + 16LL))(v15);
    v15 = 0;
  }
  v10 = v13;
  if ( v13 )
  {
    if ( i < 0 )
    {
      (*(void (**)(void))(*(_QWORD *)v13 + 32LL))();
      v10 = v13;
    }
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v10 + 16LL))(v10);
  }
  if ( v5 )
    operator delete(v5);
  return (unsigned int)i;
}

```

## disassembly

```asm
0x1800318b0  mov     [rsp-8+arg_10], rbx
0x1800318b5  push    rbp
0x1800318b6  push    rsi
0x1800318b7  push    rdi
0x1800318b8  push    r12
0x1800318ba  push    r13
0x1800318bc  push    r14
0x1800318be  push    r15
0x1800318c0  lea     rbp, [rsp-27h]
0x1800318c5  sub     rsp, 90h
0x1800318cc  mov     rax, cs:__security_cookie
0x1800318d3  xor     rax, rsp
0x1800318d6  mov     [rbp+57h+var_38], rax
0x1800318da  mov     r15, rdx
0x1800318dd  mov     r12, rcx
0x1800318e0  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x1800318e4  jnz     short loc_1800318F0
0x1800318e6  mov     eax, 80004005h
0x1800318eb  jmp     loc_180031C72
0x1800318f0  xor     r13d, r13d
0x1800318f3  lea     rcx, [rbp+57h+var_80]
0x1800318f7  mov     [rdx], r13
0x1800318fa  mov     edi, r13d
0x1800318fd  mov     [rbp+57h+var_80], r13
0x180031901  mov     [rbp+57h+var_70], r13
0x180031905  call    ASFCreateLibrary
0x18003190a  mov     ebx, eax
0x18003190c  test    eax, eax
0x18003190e  js      loc_180031C0A
0x180031914  mov     rcx, [rbp+57h+var_80]
0x180031918  lea     r8, [rbp+57h+var_68]
0x18003191c  mov     [rbp+57h+var_68], r13
0x180031920  lea     rdx, IID_IASFLibraryPriv
0x180031927  mov     rax, [rcx]
0x18003192a  mov     rax, [rax]
0x18003192d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180031932  mov     ebx, eax
0x180031934  test    eax, eax
0x180031936  js      loc_180031C0A
0x18003193c  mov     rcx, [rbp+57h+var_68]
0x180031940  lea     rdx, [rbp+57h+var_60]
0x180031944  mov     [rbp+57h+var_60], r13
0x180031948  mov     rax, [rcx]
0x18003194b  mov     rax, [rax+18h]
0x18003194f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180031954  mov     rcx, [rbp+57h+var_68]
0x180031958  mov     ebx, eax
0x18003195a  test    rcx, rcx
0x18003195d  jz      short loc_18003196F
0x18003195f  mov     rax, [rcx]
0x180031962  mov     rax, [rax+10h]
0x180031966  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003196b  mov     [rbp+57h+var_68], r13
0x18003196f  test    ebx, ebx
0x180031971  js      loc_180031C0A
0x180031977  mov     rdx, [rbp+57h+var_60]; struct IWMSCriticalSection *
0x18003197b  lea     rcx, [rbp+57h+var_90]; this
0x18003197f  call    ??0CAutoCritSec@@QEAA@PEAUIWMSCriticalSection@@@Z; CAutoCritSec::CAutoCritSec(IWMSCriticalSection *)
0x180031984  mov     rcx, [rbp+57h+var_60]
0x180031988  test    rcx, rcx
0x18003198b  jz      short loc_18003199D
0x18003198d  mov     rax, [rcx]
0x180031990  mov     rax, [rax+10h]
0x180031994  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180031999  mov     [rbp+57h+var_60], r13
0x18003199d  mov     rcx, [rbp+57h+var_80]
0x1800319a1  lea     rdx, [rbp+57h+var_88]
0x1800319a5  mov     dword ptr [rbp+57h+var_88], r13d
0x1800319a9  mov     rax, [rcx]
0x1800319ac  mov     rax, [rax+28h]
0x1800319b0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800319b5  test    eax, eax
0x1800319b7  jns     short loc_1800319CC
0x1800319b9  mov     ebx, 8000FFFFh
0x1800319be  lea     rcx, [rbp+57h+var_90]; this
0x1800319c2  call    ??1CAutoCritSec@@QEAA@XZ; CAutoCritSec::~CAutoCritSec(void)
0x1800319c7  jmp     loc_180031C0A
0x1800319cc  xor     r9d, r9d; dwMoveMethod
0x1800319cf  xor     r8d, r8d; lpDistanceToMoveHigh
0x1800319d2  xor     edx, edx; lDistanceToMove
0x1800319d4  mov     rcx, r12; hFile
0x1800319d7  call    cs:__imp_SetFilePointer
0x1800319dd  cmp     eax, 0FFFFFFFFh
0x1800319e0  jnz     short loc_1800319E9
0x1800319e2  mov     ebx, 80004005h
0x1800319e7  jmp     short loc_1800319BE
0x1800319e9  mov     esi, r13d
0x1800319ec  mov     ebx, 0C00D07D1h
0x1800319f1  cmp     ebx, 0C00D07D1h
0x1800319f7  jnz     loc_180031B70
0x1800319fd  mov     ecx, dword ptr [rbp+57h+var_88]; unsigned __int64
0x180031a00  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x180031a05  mov     r14, rax
0x180031a08  test    rax, rax
0x180031a0b  jz      loc_180031B66
0x180031a11  test    rdi, rdi
0x180031a14  jz      short loc_180031A2C
0x180031a16  mov     r8d, esi; Size
0x180031a19  mov     rdx, rdi; Src
0x180031a1c  mov     rcx, rax; void *
0x180031a1f  call    memcpy_0
0x180031a24  mov     rcx, rdi; Block
0x180031a27  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180031a2c  mov     r8d, dword ptr [rbp+57h+var_88]
0x180031a30  lea     r9, [rbp+57h+NumberOfBytesRead]; lpNumberOfBytesRead
0x180031a34  mov     edx, esi
0x180031a36  sub     r8d, esi; nNumberOfBytesToRead
0x180031a39  add     rdx, r14; lpBuffer
0x180031a3c  mov     [rbp+57h+NumberOfBytesRead], r13d
0x180031a40  mov     rcx, r12; hFile
0x180031a43  mov     [rsp+0C0h+lpOverlapped], r13; lpOverlapped
0x180031a48  mov     rdi, r14
0x180031a4b  call    cs:__imp_ReadFile
0x180031a51  test    eax, eax
0x180031a53  jz      loc_180031B5C
0x180031a59  mov     eax, dword ptr [rbp+57h+var_88]
0x180031a5c  sub     eax, esi
0x180031a5e  cmp     [rbp+57h+NumberOfBytesRead], eax
0x180031a61  jb      loc_180031B5C
0x180031a67  mov     rcx, [rbp+57h+var_80]
0x180031a6b  lea     rdx, [rbp+57h+var_50]
0x180031a6f  mov     esi, dword ptr [rbp+57h+var_88]
0x180031a72  lea     r9, [rbp+57h+var_48]
0x180031a76  xorps   xmm0, xmm0
0x180031a79  mov     [rbp+57h+var_50], r13
0x180031a7d  movups  [rbp+57h+var_48], xmm0
0x180031a81  mov     rax, [rcx]
0x180031a84  mov     r8, r14
0x180031a87  mov     [rsp+0C0h+lpOverlapped], rdx
0x180031a8c  mov     edx, esi
0x180031a8e  mov     rax, [rax+30h]
0x180031a92  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180031a97  mov     ebx, eax
0x180031a99  test    eax, eax
0x180031a9b  js      loc_180031BFD
0x180031aa1  mov     eax, dword ptr [rbp+57h+var_50]
0x180031aa4  cmp     esi, eax
0x180031aa6  jnb     short loc_180031AB0
0x180031aa8  mov     dword ptr [rbp+57h+var_88], eax
0x180031aab  jmp     loc_1800319EC
0x180031ab0  mov     rcx, [rbp+57h+var_80]
0x180031ab4  lea     r8, [rbp+57h+var_70]
0x180031ab8  lea     rdx, [rbp+57h+var_48]
0x180031abc  mov     rax, [rcx]
0x180031abf  mov     rax, [rax+38h]
0x180031ac3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180031ac8  mov     ebx, eax
0x180031aca  test    eax, eax
0x180031acc  js      loc_180031BFD
0x180031ad2  mov     rcx, [rbp+57h+var_80]
0x180031ad6  lea     r8, [rbp+57h+var_78]
0x180031ada  mov     [rbp+57h+var_78], r13
0x180031ade  lea     rdx, IID_IASFUnknownContainer
0x180031ae5  mov     rax, [rcx]
0x180031ae8  mov     rax, [rax]
0x180031aeb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180031af0  mov     ebx, eax
0x180031af2  test    eax, eax
0x180031af4  js      loc_180031BFD
0x180031afa  mov     rcx, [rbp+57h+var_78]
0x180031afe  lea     rdx, GUID_NULL
0x180031b05  mov     r8, [rbp+57h+var_70]
0x180031b09  or      r9d, 0FFFFFFFFh
0x180031b0d  mov     rax, [rcx]
0x180031b10  mov     rax, [rax+28h]
0x180031b14  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180031b19  mov     rcx, [rbp+57h+var_78]
0x180031b1d  mov     ebx, eax
0x180031b1f  test    rcx, rcx
0x180031b22  jz      short loc_180031B34
0x180031b24  mov     rax, [rcx]
0x180031b27  mov     rax, [rax+10h]
0x180031b2b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180031b30  mov     [rbp+57h+var_78], r13
0x180031b34  test    ebx, ebx
0x180031b36  js      loc_180031BFD
0x180031b3c  mov     rcx, [rbp+57h+var_70]
0x180031b40  lea     r9, [rbp+57h+var_88]
0x180031b44  mov     r8, r14
0x180031b47  mov     edx, esi
0x180031b49  mov     rax, [rcx]
0x180031b4c  mov     rax, [rax+40h]
0x180031b50  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180031b55  mov     ebx, eax
0x180031b57  jmp     loc_1800319F1
0x180031b5c  mov     ebx, 0C00D07E2h
0x180031b61  jmp     loc_180031BFD
0x180031b66  mov     ebx, 8007000Eh
0x180031b6b  jmp     loc_180031BFD
0x180031b70  test    ebx, ebx
0x180031b72  js      loc_180031BFD
0x180031b78  mov     rcx, [rbp+57h+var_70]
0x180031b7c  lea     rdx, IID_IASFHeaderObject
0x180031b83  mov     r8, r15
0x180031b86  mov     rax, [rcx]
0x180031b89  mov     rax, [rax]
0x180031b8c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180031b91  mov     ebx, eax
0x180031b93  test    eax, eax
0x180031b95  js      loc_1800319BE
0x180031b9b  mov     rcx, [rbp+57h+var_80]
0x180031b9f  lea     r8, [rbp+57h+var_78]
0x180031ba3  mov     [rbp+57h+var_78], r13
0x180031ba7  lea     rdx, IID_IASFUnknownContainer
0x180031bae  mov     rax, [rcx]
0x180031bb1  mov     rax, [rax]
0x180031bb4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180031bb9  mov     ebx, eax
0x180031bbb  test    eax, eax
0x180031bbd  js      loc_1800319BE
0x180031bc3  mov     rcx, [rbp+57h+var_78]
0x180031bc7  lea     rdx, GUID_NULL
0x180031bce  mov     r8, [rbp+57h+var_70]
0x180031bd2  or      r9d, 0FFFFFFFFh
0x180031bd6  mov     rax, [rcx]
0x180031bd9  mov     rax, [rax+28h]
0x180031bdd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180031be2  mov     rcx, [rbp+57h+var_78]
0x180031be6  mov     ebx, eax
0x180031be8  test    rcx, rcx
0x180031beb  jz      short loc_180031BFD
0x180031bed  mov     rax, [rcx]
0x180031bf0  mov     rax, [rax+10h]
0x180031bf4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180031bf9  mov     [rbp+57h+var_78], r13
0x180031bfd  lea     rcx, [rbp+57h+var_90]; this
0x180031c01  call    ??1CAutoCritSec@@QEAA@XZ; CAutoCritSec::~CAutoCritSec(void)
0x180031c06  test    ebx, ebx
0x180031c08  jns     short loc_180031C21
0x180031c0a  mov     rcx, [r15]
0x180031c0d  test    rcx, rcx
0x180031c10  jz      short loc_180031C21
0x180031c12  mov     rax, [rcx]
0x180031c15  mov     rax, [rax+10h]
0x180031c19  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180031c1e  mov     [r15], r13
0x180031c21  mov     rcx, [rbp+57h+var_70]
0x180031c25  test    rcx, rcx
0x180031c28  jz      short loc_180031C3A
0x180031c2a  mov     rax, [rcx]
0x180031c2d  mov     rax, [rax+10h]
0x180031c31  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180031c36  mov     [rbp+57h+var_70], r13
0x180031c3a  mov     rcx, [rbp+57h+var_80]
0x180031c3e  test    rcx, rcx
0x180031c41  jz      short loc_180031C63
0x180031c43  test    ebx, ebx
0x180031c45  jns     short loc_180031C57
0x180031c47  mov     rax, [rcx]
0x180031c4a  mov     rax, [rax+20h]
0x180031c4e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180031c53  mov     rcx, [rbp+57h+var_80]
0x180031c57  mov     rax, [rcx]
0x180031c5a  mov     rax, [rax+10h]
0x180031c5e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180031c63  test    rdi, rdi
0x180031c66  jz      short loc_180031C70
0x180031c68  mov     rcx, rdi; Block
0x180031c6b  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180031c70  mov     eax, ebx
0x180031c72  mov     rcx, [rbp+57h+var_38]
0x180031c76  xor     rcx, rsp; StackCookie
0x180031c79  call    __security_check_cookie
0x180031c7e  mov     rbx, [rsp+0C0h+arg_10]
0x180031c86  add     rsp, 90h
0x180031c8d  pop     r15
0x180031c8f  pop     r14
0x180031c91  pop     r13
0x180031c93  pop     r12
0x180031c95  pop     rdi
0x180031c96  pop     rsi
0x180031c97  pop     rbp
0x180031c98  retn
```
