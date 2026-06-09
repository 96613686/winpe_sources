# CBaseTmInstance::InstallContact(ushort const *,_GUID const &,_GUID,int)

- ea: `0x180077430`
- end: `0x1800777d3`
- name: `?InstallContact@CBaseTmInstance@@IEAAJPEBGAEBU_GUID@@U2@H@Z`
- size: `931`
- prototype: `int(CBaseTmInstance *__hidden this, const unsigned __int16 *, const struct _GUID *, struct _GUID *__struct_ptr, int)`
- caller_count: `1`
- callee_count: `9`
- tags: `authz_impersonation, service_task, installer_update, broker_com_uri`

## callers

- `0x180052e70`

## callees

- `0x180010944`
- `0x18001156c`
- `0x18007168c`
- `0x1800716e0`
- `0x1800762c8`
- `0x180077430`
- `0x180081d92`
- `0x180081dd0`
- `0x180085010`

## import_xrefs

- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpW` at `0x180077698`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpW` at `0x180077698`

## string_xrefs

- `0x180077771`: `com\complus\dtc\shared\util\basetminstance.cpp`
- `0x18007774c`: `Service`
- `0x180077550`: `CBaseTmInstance::InstallContact, pContactPool->Create failed`
- `0x1800774a5`: `CBaseTmInstance::InstallContact, GetContactPool failed`
- `0x1800775b6`: `CBaseTmInstance::InstallContact, SetServiceId failed`
- `0x180077584`: `CBaseTmInstance::InstallContact, pContProps->QueryInterface failed`
- `0x180077609`: `CBaseTmInstance::InstallContact, SetDescription failed`
- `0x1800775db`: `CBaseTmInstance::InstallContact, DuplicateString failed`
- `0x18007767f`: `CBaseTmInstance::InstallContact, pContactPool->WriteW failed`
- `0x18007764e`: `CBaseTmInstance::InstallContact, SetClassId failed`
- `0x180077725`: `CBaseTmInstance::InstallContact, SetContactPropertyString(DTC_GET_LOG_SIZE_W) failed`
- `0x1800776e2`: `CBaseTmInstance::InstallContact, SetContactPropertyString(DTC_LOG_PATH_W) failed`
- `0x18007776a`: `CBaseTmInstance::InstallContact, SetContactPropertyString(DTC_SVC_PATH_W) failed`

## pseudocode

```c
__int64 __fastcall CBaseTmInstance::InstallContact(
        CBaseTmInstance *this,
        const unsigned __int16 *a2,
        const struct _GUID *a3,
        struct _GUID *a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *v7)(CBaseTmInstance *, GUID *, struct IContactPool **); // rax
  int v10; // eax
  int v11; // ebx
  unsigned int v12; // r9d
  unsigned __int16 *v13; // rdx
  CBaseTmInstance *v14; // rcx
  __int64 (__fastcall *v15)(CBaseTmInstance *, const WCHAR *, const wchar_t *, const wchar_t *, unsigned __int16 *); // rbx
  unsigned __int16 *DefaultLogPath; // rax
  __int64 (__fastcall *v17)(CBaseTmInstance *, const WCHAR *, const wchar_t *, const wchar_t *, unsigned __int16 *); // rbx
  unsigned __int16 *DefaultServicePath; // rax
  CBaseTmInstance *v20; // [rsp+30h] [rbp-D0h] BYREF
  struct IContactPool *v21; // [rsp+38h] [rbp-C8h] BYREF
  char *v22; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v23; // [rsp+48h] [rbp-B8h] BYREF
  _WORD v24[256]; // [rsp+50h] [rbp-B0h] BYREF

  v4 = *(_QWORD *)this;
  v22 = 0;
  v21 = 0;
  v20 = 0;
  v7 = *(__int64 (__fastcall **)(CBaseTmInstance *, GUID *, struct IContactPool **))(v4 + 136);
  v23 = 0;
  v10 = v7(this, &IID_IContactPool, &v21);
  v11 = v10;
  if ( v10 < 0 )
  {
    v12 = 994;
    v13 = L"CBaseTmInstance::InstallContact, GetContactPool failed";
LABEL_30:
    TraceFileW(v10, v13, L"com\\complus\\dtc\\shared\\util\\basetminstance.cpp", v12);
    goto LABEL_31;
  }
  if ( (*(int (__fastcall **)(CBaseTmInstance *, const unsigned __int16 *, CBaseTmInstance **))(*(_QWORD *)this + 144LL))(
         this,
         a2,
         &v20) < 0
    || (v11 = (*(__int64 (__fastcall **)(CBaseTmInstance *, _WORD *, __int64))(*(_QWORD *)v20 + 72LL))(v20, v24, 256),
        v11 < 0)
    || v24[0] )
  {
    v14 = v20;
    if ( v20 )
    {
      (*(void (__fastcall **)(CBaseTmInstance *))(*(_QWORD *)v20 + 16LL))(v20);
      v20 = 0;
    }
    CBaseTmInstance::DeleteContacts(v14, v21, a2);
    v10 = (*(__int64 (__fastcall **)(struct IContactPool *, _QWORD, GUID *, CBaseTmInstance **))(*(_QWORD *)v21 + 56LL))(
            v21,
            0,
            &IID_IProperties,
            &v20);
    v11 = v10;
    if ( v10 >= 0 )
    {
      v10 = (**(__int64 (__fastcall ***)(CBaseTmInstance *, GUID *, __int64 *))v20)(v20, &IID_ICustomProperties, &v23);
      v11 = v10;
      if ( v10 >= 0 )
      {
        v10 = (*(__int64 (__fastcall **)(CBaseTmInstance *, const struct _GUID *, __int64))(*(_QWORD *)v20 + 120LL))(
                v20,
                a3,
                1);
        v11 = v10;
        if ( v10 >= 0 )
        {
          v10 = DuplicateString(a2, &v22);
          v11 = v10;
          if ( v10 >= 0 )
          {
            v10 = (*(__int64 (__fastcall **)(CBaseTmInstance *, char *))(*(_QWORD *)v20 + 48LL))(v20, v22);
            v11 = v10;
            if ( v10 >= 0 )
            {
              if ( !memcmp_0(a4, &GUID_NULL, 0x10u)
                || (v10 = (*(__int64 (__fastcall **)(CBaseTmInstance *, struct _GUID *))(*(_QWORD *)v20 + 104LL))(
                            v20,
                            a4),
                    v11 = v10,
                    v10 >= 0) )
              {
                v10 = (*(__int64 (__fastcall **)(struct IContactPool *, CBaseTmInstance *, _QWORD))(*(_QWORD *)v21 + 64LL))(
                        v21,
                        v20,
                        0);
                v11 = v10;
                if ( v10 >= 0 )
                {
                  if ( lstrcmpW(a2, L"MSDTC") )
                    goto LABEL_31;
                  v15 = *(__int64 (__fastcall **)(CBaseTmInstance *, const WCHAR *, const wchar_t *, const wchar_t *, unsigned __int16 *))(*(_QWORD *)this + 216LL);
                  DefaultLogPath = GetDefaultLogPath();
                  v10 = v15(this, L"MSDTC", L"LOG", L"Path", DefaultLogPath);
                  v11 = v10;
                  if ( v10 )
                  {
                    v12 = 1070;
                    v13 = L"CBaseTmInstance::InstallContact, SetContactPropertyString(DTC_LOG_PATH_W) failed";
                  }
                  else
                  {
                    v10 = (*(__int64 (__fastcall **)(CBaseTmInstance *, const WCHAR *, const wchar_t *, const wchar_t *, int))(*(_QWORD *)this + 224LL))(
                            this,
                            L"MSDTC",
                            L"LOG",
                            L"Size",
                            4);
                    v11 = v10;
                    if ( v10 )
                    {
                      v12 = 1076;
                      v13 = L"CBaseTmInstance::InstallContact, SetContactPropertyString(DTC_GET_LOG_SIZE_W) failed";
                    }
                    else
                    {
                      v17 = *(__int64 (__fastcall **)(CBaseTmInstance *, const WCHAR *, const wchar_t *, const wchar_t *, unsigned __int16 *))(*(_QWORD *)this + 216LL);
                      DefaultServicePath = GetDefaultServicePath();
                      v10 = v17(this, L"MSDTC", L"Service", L"Path", DefaultServicePath);
                      v11 = v10;
                      if ( !v10 )
                        goto LABEL_31;
                      v12 = 1083;
                      v13 = L"CBaseTmInstance::InstallContact, SetContactPropertyString(DTC_SVC_PATH_W) failed";
                    }
                  }
                }
                else
                {
                  v12 = 1056;
                  v13 = L"CBaseTmInstance::InstallContact, pContactPool->WriteW failed";
                }
              }
              else
              {
                v12 = 1048;
                v13 = L"CBaseTmInstance::InstallContact, SetClassId failed";
              }
            }
            else
            {
              v12 = 1040;
              v13 = L"CBaseTmInstance::InstallContact, SetDescription failed";
            }
          }
          else
          {
            v12 = 1034;
            v13 = L"CBaseTmInstance::InstallContact, DuplicateString failed";
          }
        }
        else
        {
          v12 = 1028;
          v13 = L"CBaseTmInstance::InstallContact, SetServiceId failed";
        }
      }
      else
      {
        v12 = 1022;
        v13 = L"CBaseTmInstance::InstallContact, pContProps->QueryInterface failed";
      }
    }
    else
    {
      v12 = 1016;
      v13 = L"CBaseTmInstance::InstallContact, pContactPool->Create failed";
    }
    goto LABEL_30;
  }
LABEL_31:
  if ( v20 )
  {
    (*(void (__fastcall **)(CBaseTmInstance *))(*(_QWORD *)v20 + 16LL))(v20);
    v20 = 0;
  }
  if ( v21 )
    (*(void (__fastcall **)(struct IContactPool *))(*(_QWORD *)v21 + 16LL))(v21);
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x180077430  push    rbp
0x180077432  push    rbx
0x180077433  push    rsi
0x180077434  push    rdi
0x180077435  push    r12
0x180077437  push    r14
0x180077439  push    r15
0x18007743b  lea     rbp, [rsp-160h]
0x180077443  sub     rsp, 260h
0x18007744a  mov     rax, cs:__security_cookie
0x180077451  xor     rax, rsp
0x180077454  mov     [rbp+190h+var_40], rax
0x18007745b  mov     rax, [rcx]
0x18007745e  xor     r12d, r12d
0x180077461  mov     r15, r8
0x180077464  mov     [rsp+290h+var_250], r12
0x180077469  mov     rsi, rdx
0x18007746c  mov     [rsp+290h+var_258], r12
0x180077471  lea     r8, [rsp+290h+var_258]
0x180077476  mov     [rsp+290h+var_260], r12
0x18007747b  mov     rax, [rax+88h]
0x180077482  lea     rdx, IID_IContactPool
0x180077489  mov     r14, r9
0x18007748c  mov     [rsp+290h+var_248], r12
0x180077491  mov     rdi, rcx
0x180077494  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180077499  mov     ebx, eax
0x18007749b  test    eax, eax
0x18007749d  jns     short loc_1800774B1
0x18007749f  mov     r9d, 3E2h
0x1800774a5  lea     rdx, aCbasetminstanc_3; "CBaseTmInstance::InstallContact, GetCon"...
0x1800774ac  jmp     loc_180077771
0x1800774b1  mov     rax, [rdi]
0x1800774b4  lea     r8, [rsp+290h+var_260]
0x1800774b9  mov     rdx, rsi
0x1800774bc  mov     rcx, rdi
0x1800774bf  mov     rax, [rax+90h]
0x1800774c6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800774cb  test    eax, eax
0x1800774cd  js      short loc_1800774FD
0x1800774cf  mov     rcx, [rsp+290h+var_260]
0x1800774d4  lea     rdx, [rsp+290h+var_240]
0x1800774d9  mov     r8d, 100h
0x1800774df  mov     rax, [rcx]
0x1800774e2  mov     rax, [rax+48h]
0x1800774e6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800774eb  mov     ebx, eax
0x1800774ed  test    eax, eax
0x1800774ef  js      short loc_1800774FD
0x1800774f1  cmp     [rsp+290h+var_240], r12w
0x1800774f7  jz      loc_18007777F
0x1800774fd  mov     rcx, [rsp+290h+var_260]
0x180077502  test    rcx, rcx
0x180077505  jz      short loc_180077518
0x180077507  mov     rax, [rcx]
0x18007750a  mov     rax, [rax+10h]
0x18007750e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180077513  mov     [rsp+290h+var_260], r12
0x180077518  mov     rdx, [rsp+290h+var_258]; struct IContactPool *
0x18007751d  mov     r8, rsi; unsigned __int16 *
0x180077520  call    ?DeleteContacts@CBaseTmInstance@@AEAAXPEAUIContactPool@@PEBG@Z; CBaseTmInstance::DeleteContacts(IContactPool *,ushort const *)
0x180077525  mov     rcx, [rsp+290h+var_258]
0x18007752a  lea     r9, [rsp+290h+var_260]
0x18007752f  lea     r8, IID_IProperties
0x180077536  xor     edx, edx
0x180077538  mov     rax, [rcx]
0x18007753b  mov     rax, [rax+38h]
0x18007753f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180077544  mov     ebx, eax
0x180077546  test    eax, eax
0x180077548  jns     short loc_18007755C
0x18007754a  mov     r9d, 3F8h
0x180077550  lea     rdx, aCbasetminstanc; "CBaseTmInstance::InstallContact, pConta"...
0x180077557  jmp     loc_180077771
0x18007755c  mov     rcx, [rsp+290h+var_260]
0x180077561  lea     r8, [rsp+290h+var_248]
0x180077566  lea     rdx, IID_ICustomProperties
0x18007756d  mov     rax, [rcx]
0x180077570  mov     rax, [rax]
0x180077573  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180077578  mov     ebx, eax
0x18007757a  test    eax, eax
0x18007757c  jns     short loc_180077590
0x18007757e  mov     r9d, 3FEh
0x180077584  lea     rdx, aCbasetminstanc_18; "CBaseTmInstance::InstallContact, pContP"...
0x18007758b  jmp     loc_180077771
0x180077590  mov     rcx, [rsp+290h+var_260]
0x180077595  mov     r8d, 1
0x18007759b  mov     rdx, r15
0x18007759e  mov     rax, [rcx]
0x1800775a1  mov     rax, [rax+78h]
0x1800775a5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800775aa  mov     ebx, eax
0x1800775ac  test    eax, eax
0x1800775ae  jns     short loc_1800775C2
0x1800775b0  mov     r9d, 404h
0x1800775b6  lea     rdx, aCbasetminstanc_10; "CBaseTmInstance::InstallContact, SetSer"...
0x1800775bd  jmp     loc_180077771
0x1800775c2  lea     rdx, [rsp+290h+var_250]; char **
0x1800775c7  mov     rcx, rsi; lpWideCharStr
0x1800775ca  call    ?DuplicateString@@YAJPEBGPEAPEAD@Z; DuplicateString(ushort const *,char * *)
0x1800775cf  mov     ebx, eax
0x1800775d1  test    eax, eax
0x1800775d3  jns     short loc_1800775E7
0x1800775d5  mov     r9d, 40Ah
0x1800775db  lea     rdx, aCbasetminstanc_9; "CBaseTmInstance::InstallContact, Duplic"...
0x1800775e2  jmp     loc_180077771
0x1800775e7  mov     rcx, [rsp+290h+var_260]
0x1800775ec  mov     rdx, [rsp+290h+var_250]
0x1800775f1  mov     rax, [rcx]
0x1800775f4  mov     rax, [rax+30h]
0x1800775f8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800775fd  mov     ebx, eax
0x1800775ff  test    eax, eax
0x180077601  jns     short loc_180077615
0x180077603  mov     r9d, 410h
0x180077609  lea     rdx, aCbasetminstanc_23; "CBaseTmInstance::InstallContact, SetDes"...
0x180077610  jmp     loc_180077771
0x180077615  mov     r8d, 10h; Size
0x18007761b  lea     rdx, GUID_NULL; Buf2
0x180077622  mov     rcx, r14; Buf1
0x180077625  call    memcmp_0
0x18007762a  test    eax, eax
0x18007762c  jz      short loc_18007765A
0x18007762e  mov     rcx, [rsp+290h+var_260]
0x180077633  mov     rdx, r14
0x180077636  mov     rax, [rcx]
0x180077639  mov     rax, [rax+68h]
0x18007763d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180077642  mov     ebx, eax
0x180077644  test    eax, eax
0x180077646  jns     short loc_18007765A
0x180077648  mov     r9d, 418h
0x18007764e  lea     rdx, aCbasetminstanc_28; "CBaseTmInstance::InstallContact, SetCla"...
0x180077655  jmp     loc_180077771
0x18007765a  mov     rcx, [rsp+290h+var_258]
0x18007765f  xor     r8d, r8d
0x180077662  mov     rdx, [rsp+290h+var_260]
0x180077667  mov     rax, [rcx]
0x18007766a  mov     rax, [rax+40h]
0x18007766e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180077673  mov     ebx, eax
0x180077675  test    eax, eax
0x180077677  jns     short loc_18007768B
0x180077679  mov     r9d, 420h
0x18007767f  lea     rdx, aCbasetminstanc_25; "CBaseTmInstance::InstallContact, pConta"...
0x180077686  jmp     loc_180077771
0x18007768b  lea     r14, aMsdtc; "MSDTC"
0x180077692  mov     rcx, rsi; lpString1
0x180077695  mov     rdx, r14; lpString2
0x180077698  call    cs:__imp_lstrcmpW
0x18007769e  test    eax, eax
0x1800776a0  jnz     loc_18007777F
0x1800776a6  mov     rax, [rdi]
0x1800776a9  mov     rbx, [rax+0D8h]
0x1800776b0  call    ?GetDefaultLogPath@@YAPEAGXZ; GetDefaultLogPath(void)
0x1800776b5  mov     [rsp+290h+var_270], rax
0x1800776ba  lea     r9, aPath; "Path"
0x1800776c1  mov     rax, rbx
0x1800776c4  lea     r8, aLog; "LOG"
0x1800776cb  mov     rdx, r14
0x1800776ce  mov     rcx, rdi
0x1800776d1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800776d6  mov     ebx, eax
0x1800776d8  test    eax, eax
0x1800776da  jz      short loc_1800776EE
0x1800776dc  mov     r9d, 42Eh
0x1800776e2  lea     rdx, aCbasetminstanc_11; "CBaseTmInstance::InstallContact, SetCon"...
0x1800776e9  jmp     loc_180077771
0x1800776ee  mov     rax, [rdi]
0x1800776f1  lea     r9, aSize; "Size"
0x1800776f8  lea     r8, aLog; "LOG"
0x1800776ff  mov     dword ptr [rsp+290h+var_270], 4
0x180077707  mov     rdx, r14
0x18007770a  mov     rcx, rdi
0x18007770d  mov     rax, [rax+0E0h]
0x180077714  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180077719  mov     ebx, eax
0x18007771b  test    eax, eax
0x18007771d  jz      short loc_18007772E
0x18007771f  mov     r9d, 434h
0x180077725  lea     rdx, aCbasetminstanc_30; "CBaseTmInstance::InstallContact, SetCon"...
0x18007772c  jmp     short loc_180077771
0x18007772e  mov     rax, [rdi]
0x180077731  mov     rbx, [rax+0D8h]
0x180077738  call    ?GetDefaultServicePath@@YAPEAGXZ; GetDefaultServicePath(void)
0x18007773d  mov     [rsp+290h+var_270], rax
0x180077742  lea     r9, aPath; "Path"
0x180077749  mov     rax, rbx
0x18007774c  lea     r8, aService; "Service"
0x180077753  mov     rdx, r14
0x180077756  mov     rcx, rdi
0x180077759  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007775e  mov     ebx, eax
0x180077760  test    eax, eax
0x180077762  jz      short loc_18007777F
0x180077764  mov     r9d, 43Bh; unsigned int
0x18007776a  lea     rdx, aCbasetminstanc_6; "CBaseTmInstance::InstallContact, SetCon"...
0x180077771  lea     r8, aComComplusDtcS_3; "com\\complus\\dtc\\shared\\util\\basetm"...
0x180077778  mov     ecx, eax; int
0x18007777a  call    ?TraceFileW@@YAXJPEAGPEBGI@Z; TraceFileW(long,ushort *,ushort const *,uint)
0x18007777f  mov     rcx, [rsp+290h+var_260]
0x180077784  test    rcx, rcx
0x180077787  jz      short loc_18007779A
0x180077789  mov     rax, [rcx]
0x18007778c  mov     rax, [rax+10h]
0x180077790  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180077795  mov     [rsp+290h+var_260], r12
0x18007779a  mov     rcx, [rsp+290h+var_258]
0x18007779f  test    rcx, rcx
0x1800777a2  jz      short loc_1800777B0
0x1800777a4  mov     rax, [rcx]
0x1800777a7  mov     rax, [rax+10h]
0x1800777ab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800777b0  mov     eax, ebx
0x1800777b2  mov     rcx, [rbp+190h+var_40]
0x1800777b9  xor     rcx, rsp; StackCookie
0x1800777bc  call    __security_check_cookie
0x1800777c1  add     rsp, 260h
0x1800777c8  pop     r15
0x1800777ca  pop     r14
0x1800777cc  pop     r12
0x1800777ce  pop     rdi
0x1800777cf  pop     rsi
0x1800777d0  pop     rbx
0x1800777d1  pop     rbp
0x1800777d2  retn
```
