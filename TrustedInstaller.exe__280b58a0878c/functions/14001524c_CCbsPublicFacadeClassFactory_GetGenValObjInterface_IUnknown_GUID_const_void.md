# CCbsPublicFacadeClassFactory::GetGenValObjInterface(IUnknown *,_GUID const &,void * *)

- ea: `0x14001524c`
- end: `0x140015395`
- name: `?GetGenValObjInterface@CCbsPublicFacadeClassFactory@@AEAAJPEAUIUnknown@@AEBU_GUID@@PEAPEAX@Z`
- size: `329`
- prototype: `__int64 __fastcall(LPVOID *this, struct IUnknown *, const struct _GUID *, void **)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x140014334`

## callees

- `0x1400023e0`
- `0x1400148e8`
- `0x14001524c`
- `0x140017658`
- `0x14002b010`

## string_xrefs

- `0x1400152a6`: `Failed to create IAdminGenuineCheck`
- `0x14001538c`: `Failed to create IAdminGenuineCheck from cached classfactory`

## pseudocode

```c
__int64 __fastcall CCbsPublicFacadeClassFactory::GetGenValObjInterface(
        LPVOID *this,
        struct IUnknown *a2,
        const struct _GUID *a3,
        void **a4)
{
  unsigned int v6; // ebx
  LPVOID *v7; // rdi
  int InstanceFromProtectedProcess; // eax
  const char *v9; // r9
  __int64 v11; // [rsp+30h] [rbp-28h] BYREF

  v11 = 0;
  if ( !a4 )
  {
    v6 = -2147467261;
    CBSWdsLogLight(0x4000000u, 0x80004003, (size_t *)1, "No object result specified");
    goto LABEL_14;
  }
  v7 = this + 4;
  if ( !this[4] )
  {
    InstanceFromProtectedProcess = CCbsPublicFacadeClassFactory::CreateInstanceFromProtectedProcess(this + 4);
    v6 = InstanceFromProtectedProcess;
    if ( InstanceFromProtectedProcess < 0 )
      goto LABEL_5;
  }
  InstanceFromProtectedProcess = (*(__int64 (__fastcall **)(LPVOID, _QWORD, GUID *, __int64 *))(*(_QWORD *)*v7 + 24LL))(
                                   *v7,
                                   0,
                                   &GUID_1069b656_07f8_41d6_9b1c_6b1f43a8a4a1,
                                   &v11);
  v6 = InstanceFromProtectedProcess;
  if ( InstanceFromProtectedProcess == -2147023174 )
  {
    if ( *v7 )
      (*(void (__fastcall **)(LPVOID))(*(_QWORD *)*v7 + 16LL))(*v7);
    InstanceFromProtectedProcess = CCbsPublicFacadeClassFactory::CreateInstanceFromProtectedProcess(v7);
    v6 = InstanceFromProtectedProcess;
    if ( InstanceFromProtectedProcess < 0
      || (InstanceFromProtectedProcess = (*(__int64 (__fastcall **)(LPVOID, _QWORD, GUID *, __int64 *))(*(_QWORD *)*v7 + 24LL))(
                                           *v7,
                                           0,
                                           &GUID_1069b656_07f8_41d6_9b1c_6b1f43a8a4a1,
                                           &v11),
          v6 = InstanceFromProtectedProcess,
          InstanceFromProtectedProcess < 0) )
    {
LABEL_5:
      v9 = "Failed to create IAdminGenuineCheck";
      goto LABEL_13;
    }
  }
  else if ( InstanceFromProtectedProcess < 0 )
  {
    v9 = "Failed to create IAdminGenuineCheck from cached classfactory";
    goto LABEL_13;
  }
  InstanceFromProtectedProcess = (**(__int64 (__fastcall ***)(__int64, const struct _GUID *, void **))v11)(v11, a3, a4);
  v6 = InstanceFromProtectedProcess;
  if ( InstanceFromProtectedProcess >= 0 )
    goto LABEL_14;
  v9 = "Failed to query IAdminGenuineCheck";
LABEL_13:
  CBSWdsLogLight(0x4000000u, (unsigned int)InstanceFromProtectedProcess, (size_t *)1, v9);
LABEL_14:
  if ( v11 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v11 + 16LL))(v11);
  return v6;
}

```

## disassembly

```asm
0x14001524c  mov     [rsp+arg_8], rbx
0x140015251  push    rbp
0x140015252  push    rsi
0x140015253  push    rdi
0x140015254  sub     rsp, 40h
0x140015258  mov     rax, cs:__security_cookie
0x14001525f  xor     rax, rsp
0x140015262  mov     [rsp+58h+var_20], rax
0x140015267  mov     [rsp+58h+var_28], 0
0x140015270  mov     rsi, r9
0x140015273  mov     rbp, r8
0x140015276  test    r9, r9
0x140015279  jnz     short loc_14001528E
0x14001527b  mov     ebx, 80004003h
0x140015280  lea     r9, aNoObjectResult; "No object result specified"
0x140015287  mov     edx, ebx
0x140015289  jmp     loc_140015346
0x14001528e  lea     rdi, [rcx+20h]
0x140015292  cmp     qword ptr [rdi], 0
0x140015296  jnz     short loc_1400152B2
0x140015298  mov     rcx, rdi; struct IClassFactory **
0x14001529b  call    ?CreateInstanceFromProtectedProcess@CCbsPublicFacadeClassFactory@@CAJPEAPEAUIClassFactory@@@Z; CCbsPublicFacadeClassFactory::CreateInstanceFromProtectedProcess(IClassFactory * *)
0x1400152a0  mov     ebx, eax
0x1400152a2  test    eax, eax
0x1400152a4  jns     short loc_1400152B2
0x1400152a6  lea     r9, aFailedToCreate_17; "Failed to create IAdminGenuineCheck"
0x1400152ad  jmp     loc_140015344
0x1400152b2  mov     rcx, [rdi]
0x1400152b5  lea     r9, [rsp+58h+var_28]
0x1400152ba  lea     r8, _GUID_1069b656_07f8_41d6_9b1c_6b1f43a8a4a1
0x1400152c1  xor     edx, edx
0x1400152c3  mov     rax, [rcx]
0x1400152c6  mov     rax, [rax+18h]
0x1400152ca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400152cf  mov     ebx, eax
0x1400152d1  cmp     eax, 800706BAh
0x1400152d6  jnz     loc_140015388
0x1400152dc  mov     rcx, [rdi]
0x1400152df  test    rcx, rcx
0x1400152e2  jz      short loc_1400152F0
0x1400152e4  mov     rax, [rcx]
0x1400152e7  mov     rax, [rax+10h]
0x1400152eb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400152f0  mov     rcx, rdi; struct IClassFactory **
0x1400152f3  call    ?CreateInstanceFromProtectedProcess@CCbsPublicFacadeClassFactory@@CAJPEAPEAUIClassFactory@@@Z; CCbsPublicFacadeClassFactory::CreateInstanceFromProtectedProcess(IClassFactory * *)
0x1400152f8  mov     ebx, eax
0x1400152fa  test    eax, eax
0x1400152fc  js      short loc_1400152A6
0x1400152fe  mov     rcx, [rdi]
0x140015301  lea     r9, [rsp+58h+var_28]
0x140015306  lea     r8, _GUID_1069b656_07f8_41d6_9b1c_6b1f43a8a4a1
0x14001530d  xor     edx, edx
0x14001530f  mov     rax, [rcx]
0x140015312  mov     rax, [rax+18h]
0x140015316  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001531b  mov     ebx, eax
0x14001531d  test    eax, eax
0x14001531f  js      short loc_1400152A6
0x140015321  mov     rcx, [rsp+58h+var_28]
0x140015326  mov     r8, rsi
0x140015329  mov     rdx, rbp
0x14001532c  mov     rax, [rcx]
0x14001532f  mov     rax, [rax]
0x140015332  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140015337  mov     ebx, eax
0x140015339  test    eax, eax
0x14001533b  jns     short loc_140015356
0x14001533d  lea     r9, aFailedToQueryI; "Failed to query IAdminGenuineCheck"
0x140015344  mov     edx, eax
0x140015346  mov     r8d, 1
0x14001534c  mov     ecx, 4000000h
0x140015351  call    ?CBSWdsLogLight@@YAXW4tagLOG_SETUPLOG_SEVERITY@@J_NPEBDZZ; CBSWdsLogLight(tagLOG_SETUPLOG_SEVERITY,long,bool,char const *,...)
0x140015356  mov     rcx, [rsp+58h+var_28]
0x14001535b  test    rcx, rcx
0x14001535e  jz      short loc_14001536C
0x140015360  mov     rax, [rcx]
0x140015363  mov     rax, [rax+10h]
0x140015367  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001536c  mov     eax, ebx
0x14001536e  mov     rcx, [rsp+58h+var_20]
0x140015373  xor     rcx, rsp; StackCookie
0x140015376  call    __security_check_cookie
0x14001537b  mov     rbx, [rsp+58h+arg_8]
0x140015380  add     rsp, 40h
0x140015384  pop     rdi
0x140015385  pop     rsi
0x140015386  pop     rbp
0x140015387  retn
0x140015388  test    eax, eax
0x14001538a  jns     short loc_140015321
0x14001538c  lea     r9, aFailedToCreate_24; "Failed to create IAdminGenuineCheck fro"...
0x140015393  jmp     short loc_140015344
```
