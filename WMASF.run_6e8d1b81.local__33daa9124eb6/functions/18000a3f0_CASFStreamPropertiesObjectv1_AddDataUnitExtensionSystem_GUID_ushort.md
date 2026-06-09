# CASFStreamPropertiesObjectv1::AddDataUnitExtensionSystem(_GUID,ushort)

- ea: `0x18000a3f0`
- end: `0x18000a592`
- name: `?AddDataUnitExtensionSystem@CASFStreamPropertiesObjectv1@@UEAAJU_GUID@@G@Z`
- size: `418`
- prototype: `__int64 __fastcall(CASFStreamPropertiesObjectv1 *__hidden this, struct _GUID *__struct_ptr, unsigned __int16)`
- caller_count: `0`
- callee_count: `5`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x1800015d0`
- `0x1800021dc`
- `0x18000220c`
- `0x18000a3f0`
- `0x180040010`

## pseudocode

```c
__int64 __fastcall CASFStreamPropertiesObjectv1::AddDataUnitExtensionSystem(
        CASFStreamPropertiesObjectv1 *this,
        struct _GUID *a2,
        unsigned __int16 a3)
{
  __int128 v3; // xmm0
  struct IWMSCriticalSection *v4; // rdx
  __int64 v7; // rcx
  int v8; // ebx
  __int64 v9; // rcx
  int v10; // eax
  _BYTE v12[8]; // [rsp+30h] [rbp-30h] BYREF
  __int64 v13; // [rsp+38h] [rbp-28h] BYREF
  __int64 v14; // [rsp+40h] [rbp-20h] BYREF
  __int128 v15; // [rsp+48h] [rbp-18h] BYREF

  v3 = (__int128)*a2;
  v4 = (struct IWMSCriticalSection *)*((_QWORD *)this - 50);
  v15 = v3;
  CAutoCritSec::CAutoCritSec((CAutoCritSec *)v12, v4);
  v7 = *((_QWORD *)this - 49);
  if ( v7 )
  {
    v14 = 0;
    v13 = 0;
    v8 = (*(__int64 (__fastcall **)(__int64, GUID *, __int64 *))(*(_QWORD *)v7 + 56LL))(
           v7,
           &CLSID_ASFDataUnitExtensionObject,
           &v14);
    if ( v8 >= 0 )
    {
      v8 = (**(__int64 (__fastcall ***)(__int64, GUID *, __int64 *))v14)(v14, &IID_IASFDataUnitExtensionObject, &v13);
      if ( v8 >= 0 )
      {
        v8 = (*(__int64 (__fastcall **)(_QWORD, GUID *, __int64, __int64))(**((_QWORD **)this - 44) + 40LL))(
               *((_QWORD *)this - 44),
               &CLSID_ASFDataUnitExtensionObject,
               v14,
               0xFFFFFFFFLL);
        if ( v14 )
        {
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v14 + 16LL))(v14);
          v14 = 0;
        }
        v9 = v13;
        if ( v8 < 0
          || (v10 = (*(__int64 (__fastcall **)(__int64, __int128 *))(*(_QWORD *)v13 + 88LL))(v13, &v15),
              v9 = v13,
              v8 = v10,
              v10 < 0) )
        {
          if ( v9 )
          {
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v9 + 16LL))(v9);
            v13 = 0;
          }
        }
        else
        {
          v8 = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v13 + 104LL))(v13, a3);
          if ( v13 )
          {
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v13 + 16LL))(v13);
            v13 = 0;
          }
          if ( v8 >= 0 )
            v8 = 0;
        }
      }
      else if ( v14 )
      {
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v14 + 16LL))(v14);
        v14 = 0;
      }
    }
  }
  else
  {
    v8 = -1072887818;
  }
  CAutoCritSec::~CAutoCritSec((CAutoCritSec *)v12);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x18000a3f0  mov     [rsp-18h+arg_18], rbx
0x18000a3f5  push    rbp
0x18000a3f6  push    rsi
0x18000a3f7  push    rdi
0x18000a3f8  mov     rbp, rsp
0x18000a3fb  sub     rsp, 60h
0x18000a3ff  mov     rax, cs:__security_cookie
0x18000a406  xor     rax, rsp
0x18000a409  mov     [rbp+var_8], rax
0x18000a40d  movups  xmm0, xmmword ptr [rdx]
0x18000a410  mov     rdx, [rcx-190h]; struct IWMSCriticalSection *
0x18000a417  mov     rdi, rcx
0x18000a41a  lea     rcx, [rbp+var_30]; this
0x18000a41e  movzx   esi, r8w
0x18000a422  movdqu  [rbp+var_18], xmm0
0x18000a427  call    ??0CAutoCritSec@@QEAA@PEAUIWMSCriticalSection@@@Z; CAutoCritSec::CAutoCritSec(IWMSCriticalSection *)
0x18000a42c  mov     rcx, [rdi-188h]
0x18000a433  test    rcx, rcx
0x18000a436  jnz     short loc_18000A442
0x18000a438  mov     ebx, 0C00D07F6h
0x18000a43d  jmp     loc_18000A56B
0x18000a442  mov     [rbp+var_20], 0
0x18000a44a  lea     r8, [rbp+var_20]
0x18000a44e  mov     [rbp+var_28], 0
0x18000a456  lea     rdx, CLSID_ASFDataUnitExtensionObject
0x18000a45d  mov     rax, [rcx]
0x18000a460  mov     rax, [rax+38h]
0x18000a464  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a469  mov     ebx, eax
0x18000a46b  test    eax, eax
0x18000a46d  js      loc_18000A56B
0x18000a473  mov     rcx, [rbp+var_20]
0x18000a477  lea     r8, [rbp+var_28]
0x18000a47b  lea     rdx, IID_IASFDataUnitExtensionObject
0x18000a482  mov     rax, [rcx]
0x18000a485  mov     rax, [rax]
0x18000a488  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a48d  mov     ebx, eax
0x18000a48f  test    eax, eax
0x18000a491  jns     short loc_18000A4B9
0x18000a493  mov     rcx, [rbp+var_20]
0x18000a497  test    rcx, rcx
0x18000a49a  jz      loc_18000A56B
0x18000a4a0  mov     rax, [rcx]
0x18000a4a3  mov     rax, [rax+10h]
0x18000a4a7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a4ac  mov     [rbp+var_20], 0
0x18000a4b4  jmp     loc_18000A56B
0x18000a4b9  mov     rcx, [rdi-160h]
0x18000a4c0  lea     rdx, CLSID_ASFDataUnitExtensionObject
0x18000a4c7  mov     r8, [rbp+var_20]
0x18000a4cb  or      r9d, 0FFFFFFFFh
0x18000a4cf  mov     rax, [rcx]
0x18000a4d2  mov     rax, [rax+28h]
0x18000a4d6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a4db  mov     rcx, [rbp+var_20]
0x18000a4df  mov     ebx, eax
0x18000a4e1  test    rcx, rcx
0x18000a4e4  jz      short loc_18000A4FA
0x18000a4e6  mov     rax, [rcx]
0x18000a4e9  mov     rax, [rax+10h]
0x18000a4ed  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a4f2  mov     [rbp+var_20], 0
0x18000a4fa  mov     rcx, [rbp+var_28]
0x18000a4fe  test    ebx, ebx
0x18000a500  jns     short loc_18000A51D
0x18000a502  test    rcx, rcx
0x18000a505  jz      short loc_18000A56B
0x18000a507  mov     rax, [rcx]
0x18000a50a  mov     rax, [rax+10h]
0x18000a50e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a513  mov     [rbp+var_28], 0
0x18000a51b  jmp     short loc_18000A56B
0x18000a51d  mov     rax, [rcx]
0x18000a520  lea     rdx, [rbp+var_18]
0x18000a524  mov     rax, [rax+58h]
0x18000a528  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a52d  mov     rcx, [rbp+var_28]
0x18000a531  mov     ebx, eax
0x18000a533  test    eax, eax
0x18000a535  js      short loc_18000A502
0x18000a537  mov     rax, [rcx]
0x18000a53a  movzx   edx, si
0x18000a53d  mov     rax, [rax+68h]
0x18000a541  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a546  mov     rcx, [rbp+var_28]
0x18000a54a  mov     ebx, eax
0x18000a54c  test    rcx, rcx
0x18000a54f  jz      short loc_18000A565
0x18000a551  mov     rax, [rcx]
0x18000a554  mov     rax, [rax+10h]
0x18000a558  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a55d  mov     [rbp+var_28], 0
0x18000a565  test    ebx, ebx
0x18000a567  js      short loc_18000A56B
0x18000a569  xor     ebx, ebx
0x18000a56b  lea     rcx, [rbp+var_30]; this
0x18000a56f  call    ??1CAutoCritSec@@QEAA@XZ; CAutoCritSec::~CAutoCritSec(void)
0x18000a574  mov     eax, ebx
0x18000a576  mov     rcx, [rbp+var_8]
0x18000a57a  xor     rcx, rsp; StackCookie
0x18000a57d  call    __security_check_cookie
0x18000a582  mov     rbx, [rsp+60h+arg_18]
0x18000a58a  add     rsp, 60h
0x18000a58e  pop     rdi
0x18000a58f  pop     rsi
0x18000a590  pop     rbp
0x18000a591  retn
```
