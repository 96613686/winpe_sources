# CComponentObject::TryInstantiate(CHitObj *)

- ea: `0x18003929c`
- end: `0x180039420`
- name: `?TryInstantiate@CComponentObject@@AEAAJPEAVCHitObj@@@Z`
- size: `388`
- prototype: `__int64 __fastcall(CComponentObject *__hidden this, struct CHitObj *)`
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x180038438`

## callees

- `0x18003776c`
- `0x180037974`
- `0x180037f34`
- `0x18003929c`
- `0x180060b20`
- `0x180062d14`
- `0x180064010`

## import_xrefs

- `ole32!CoCreateInstance` at `0x180039340`
- `ole32!CoCreateInstance` at `0x18003937c`
- `ole32!CoCreateInstance` at `0x180039340`
- `ole32!CoCreateInstance` at `0x18003937c`

## pseudocode

```c
__int64 __fastcall CComponentObject::TryInstantiate(CComponentObject *this, struct CHitObj *a2)
{
  LPVOID *ppv; // rsi
  __int64 result; // rax
  const struct _GUID *v5; // rcx
  char v6; // al
  HRESULT Instance; // eax
  HRESULT v8; // edi
  CTypelibCache *v9; // rcx
  struct CHitObj *v10; // [rsp+68h] [rbp+10h] BYREF

  v10 = a2;
  ppv = (LPVOID *)((char *)this + 56);
  if ( *((_QWORD *)this + 7) )
    return 0;
  if ( (*((_DWORD *)this + 10) & 0x8000) != 0 )
    return 2147500037LL;
  if ( (*((_DWORD *)this + 10) & 0xF00) == 0 )
  {
    v5 = (const struct _GUID *)((char *)this + 64);
    if ( *(_QWORD *)&v5->Data1 != *(_QWORD *)&GUID_NULL.Data1 || *(_QWORD *)v5->Data4 != *(_QWORD *)GUID_NULL.Data4 )
    {
      LODWORD(v10) = 0;
      result = CompModelFromCLSID(v5, (unsigned int *)&v10, 0);
      if ( (int)result < 0 )
        return result;
      v6 = (char)v10;
      *((_DWORD *)this + 10) &= 0xFFFFF0FF;
      *((_DWORD *)this + 10) |= (v6 & 0xF) << 8;
    }
  }
  Instance = CoCreateInstance((const IID *const)this + 4, 0, 0x15u, &IID_IUnknown, ppv);
  v9 = (CTypelibCache *)*((unsigned int *)this + 10);
  v8 = Instance;
  LOBYTE(v9) = (unsigned __int8)v9 & 0xF0;
  if ( (_BYTE)v9 != 16 )
  {
LABEL_14:
    if ( v8 < 0 )
      return (unsigned int)v8;
    goto LABEL_15;
  }
  if ( Instance < 0 )
  {
    if ( CTypelibCache::UpdateMappedCLSID(v9, (struct _GUID *)this + 4) )
      return (unsigned int)v8;
    v8 = CoCreateInstance((const IID *const)this + 4, 0, 0x15u, &IID_IUnknown, ppv);
    goto LABEL_14;
  }
LABEL_15:
  if ( (_BYTE)xmmword_180079F90 && (*((_DWORD *)this + 10) & 0xF00) == 0x800 )
    *((_DWORD *)this + 10) |= 0x1000u;
  else
    *((_DWORD *)this + 10) ^= (*((_DWORD *)this + 10)
                             ^ ((unsigned int)ViperCoObjectAggregatesFTM((struct IUnknown *)*ppv) << 12))
                            & 0x1000;
  v8 = (**(__int64 (__fastcall ***)(LPVOID, GUID *, char *))*ppv)(*ppv, &IID_IDispatch, (char *)this + 48);
  if ( v8 >= 0 )
  {
    if ( (*((_DWORD *)this + 10) & 0xFu) - 1 <= 1 && (*((_DWORD *)this + 10) & 0x101000) == 0 )
      return CComponentObject::ConvertToGIPCookie(this);
    if ( (*((_DWORD *)this + 10) & 0x2000) == 0 )
      CComponentObject::GetOnPageInfo(this);
  }
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x18003929c  mov     [rsp+arg_8], rdx
0x1800392a1  push    rbx
0x1800392a2  push    rbp
0x1800392a3  push    rsi
0x1800392a4  push    rdi
0x1800392a5  sub     rsp, 38h
0x1800392a9  lea     rsi, [rcx+38h]
0x1800392ad  mov     rbx, rcx
0x1800392b0  cmp     qword ptr [rsi], 0
0x1800392b4  jz      short loc_1800392BD
0x1800392b6  xor     eax, eax
0x1800392b8  jmp     loc_180039417
0x1800392bd  test    dword ptr [rcx+28h], 8000h
0x1800392c4  jz      short loc_1800392D0
0x1800392c6  mov     eax, 80004005h
0x1800392cb  jmp     loc_180039417
0x1800392d0  test    dword ptr [rcx+28h], 0F00h
0x1800392d7  jnz     short loc_180039327
0x1800392d9  add     rcx, 40h ; '@'; struct _GUID *
0x1800392dd  mov     rax, [rcx]
0x1800392e0  cmp     rax, qword ptr cs:GUID_NULL.Data1
0x1800392e7  jnz     short loc_1800392F6
0x1800392e9  mov     rax, [rcx+8]
0x1800392ed  cmp     rax, qword ptr cs:GUID_NULL.Data4
0x1800392f4  jz      short loc_180039327
0x1800392f6  xor     r8d, r8d; int *
0x1800392f9  mov     dword ptr [rsp+58h+arg_8], 0
0x180039301  lea     rdx, [rsp+58h+arg_8]; unsigned int *
0x180039306  call    ?CompModelFromCLSID@@YAJAEBU_GUID@@PEAKPEAH@Z; CompModelFromCLSID(_GUID const &,ulong *,int *)
0x18003930b  test    eax, eax
0x18003930d  js      loc_180039417
0x180039313  mov     eax, dword ptr [rsp+58h+arg_8]
0x180039317  and     dword ptr [rbx+28h], 0FFFFF0FFh
0x18003931e  and     eax, 0Fh
0x180039321  shl     eax, 8
0x180039324  or      [rbx+28h], eax
0x180039327  xor     edx, edx; pUnkOuter
0x180039329  mov     [rsp+58h+ppv], rsi; ppv
0x18003932e  lea     rbp, [rbx+40h]
0x180039332  lea     r9, IID_IUnknown; riid
0x180039339  mov     rcx, rbp; rclsid
0x18003933c  lea     r8d, [rdx+15h]; dwClsContext
0x180039340  call    cs:__imp_CoCreateInstance
0x180039346  mov     ecx, [rbx+28h]
0x180039349  mov     edi, eax
0x18003934b  and     cl, 0F0h; this
0x18003934e  cmp     cl, 10h
0x180039351  jnz     short loc_180039384
0x180039353  test    eax, eax
0x180039355  jns     short loc_18003938C
0x180039357  mov     rdx, rbp; struct _GUID *
0x18003935a  call    ?UpdateMappedCLSID@CTypelibCache@@QEAAJPEAU_GUID@@@Z; CTypelibCache::UpdateMappedCLSID(_GUID *)
0x18003935f  test    eax, eax
0x180039361  jnz     loc_180039415
0x180039367  lea     r9, IID_IUnknown; riid
0x18003936e  mov     [rsp+58h+ppv], rsi; ppv
0x180039373  xor     edx, edx; pUnkOuter
0x180039375  lea     r8d, [rax+15h]; dwClsContext
0x180039379  mov     rcx, rbp; rclsid
0x18003937c  call    cs:__imp_CoCreateInstance
0x180039382  mov     edi, eax
0x180039384  test    edi, edi
0x180039386  js      loc_180039415
0x18003938c  cmp     byte ptr cs:xmmword_180079F90, 0
0x180039393  jz      short loc_1800393AF
0x180039395  mov     ecx, [rbx+28h]
0x180039398  mov     eax, ecx
0x18003939a  and     eax, 0F00h
0x18003939f  cmp     eax, 800h
0x1800393a4  jnz     short loc_1800393AF
0x1800393a6  bts     ecx, 0Ch
0x1800393aa  mov     [rbx+28h], ecx
0x1800393ad  jmp     short loc_1800393C5
0x1800393af  mov     rcx, [rsi]; struct IUnknown *
0x1800393b2  call    ?ViperCoObjectAggregatesFTM@@YAHPEAUIUnknown@@@Z; ViperCoObjectAggregatesFTM(IUnknown *)
0x1800393b7  shl     eax, 0Ch
0x1800393ba  xor     eax, [rbx+28h]
0x1800393bd  and     eax, 1000h
0x1800393c2  xor     [rbx+28h], eax
0x1800393c5  mov     rcx, [rsi]
0x1800393c8  lea     r8, [rbx+30h]
0x1800393cc  lea     rdx, IID_IDispatch
0x1800393d3  mov     rax, [rcx]
0x1800393d6  mov     rax, [rax]
0x1800393d9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800393de  mov     edi, eax
0x1800393e0  test    eax, eax
0x1800393e2  js      short loc_180039415
0x1800393e4  mov     eax, [rbx+28h]
0x1800393e7  and     eax, 0Fh
0x1800393ea  dec     eax
0x1800393ec  cmp     eax, 1
0x1800393ef  ja      short loc_180039404
0x1800393f1  test    dword ptr [rbx+28h], 101000h
0x1800393f8  jnz     short loc_180039404
0x1800393fa  mov     rcx, rbx; this
0x1800393fd  call    ?ConvertToGIPCookie@CComponentObject@@AEAAJXZ; CComponentObject::ConvertToGIPCookie(void)
0x180039402  jmp     short loc_180039417
0x180039404  test    dword ptr [rbx+28h], 2000h
0x18003940b  jnz     short loc_180039415
0x18003940d  mov     rcx, rbx; this
0x180039410  call    ?GetOnPageInfo@CComponentObject@@AEAAJXZ; CComponentObject::GetOnPageInfo(void)
0x180039415  mov     eax, edi
0x180039417  add     rsp, 38h
0x18003941b  pop     rdi
0x18003941c  pop     rsi
0x18003941d  pop     rbp
0x18003941e  pop     rbx
0x18003941f  retn
```
