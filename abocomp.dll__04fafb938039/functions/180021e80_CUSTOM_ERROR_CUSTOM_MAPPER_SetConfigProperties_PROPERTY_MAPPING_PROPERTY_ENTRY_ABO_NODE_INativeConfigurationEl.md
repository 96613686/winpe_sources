# CUSTOM_ERROR_CUSTOM_MAPPER::SetConfigProperties(PROPERTY_MAPPING *,PROPERTY_ENTRY *,ABO_NODE *,INativeConfigurationElement *)

- ea: `0x180021e80`
- end: `0x18002218a`
- name: `?SetConfigProperties@CUSTOM_ERROR_CUSTOM_MAPPER@@UEAAJPEAVPROPERTY_MAPPING@@PEAVPROPERTY_ENTRY@@PEAVABO_NODE@@PEAVINativeConfigurationElement@@@Z`
- size: `778`
- prototype: `__int64 __fastcall(CUSTOM_ERROR_CUSTOM_MAPPER *__hidden this, struct PROPERTY_MAPPING *, struct PROPERTY_ENTRY *, struct ABO_NODE *, struct INativeConfigurationElement *)`
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config`

## callees

- `0x180003460`
- `0x18001ce3c`
- `0x180021e80`
- `0x18002c010`

## import_xrefs

- `iisutil!?QueryStr@STRU@@QEBAPEBGXZ` at `0x180022095`
- `iisutil!?QueryStr@STRU@@QEBAPEBGXZ` at `0x180022095`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x180021faf`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x180021faf`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180022113`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180022129`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180022113`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180022129`
- `iisutil!??0STRU@@QEAA@XZ` at `0x180021fc2`
- `iisutil!??0STRU@@QEAA@XZ` at `0x180021fc2`

## pseudocode

```c
__int64 __fastcall CUSTOM_ERROR_CUSTOM_MAPPER::SetConfigProperties(
        CUSTOM_ERROR_CUSTOM_MAPPER *this,
        struct PROPERTY_MAPPING *a2,
        struct PROPERTY_ENTRY *a3,
        struct ABO_NODE *a4,
        struct INativeConfigurationElement *a5)
{
  int v6; // ebx
  int v7; // edx
  int v8; // edi
  const unsigned __int16 *v9; // rdi
  __int64 (__fastcall *v10)(__int64, const wchar_t *, const unsigned __int16 *, _QWORD); // rbx
  const unsigned __int16 *Str; // rax
  int v12; // eax
  __int64 v13; // rax
  __int64 v15; // [rsp+30h] [rbp-41h] BYREF
  __int64 v16; // [rsp+38h] [rbp-39h] BYREF
  _DWORD v17[4]; // [rsp+40h] [rbp-31h] BYREF
  _BYTE v18[56]; // [rsp+50h] [rbp-21h] BYREF
  __int64 v19; // [rsp+88h] [rbp+17h]
  unsigned int v20; // [rsp+90h] [rbp+1Fh]

  v16 = 0;
  v15 = 0;
  v17[0] = 0;
  if ( a2 && a3 && a4 && a5 )
  {
    v6 = (*(__int64 (__fastcall **)(struct INativeConfigurationElement *, __int64 *))(*(_QWORD *)a5 + 40LL))(a5, &v16);
    if ( v6 >= 0 )
    {
      v6 = (*(__int64 (__fastcall **)(__int64, _DWORD *))(*(_QWORD *)v16 + 72LL))(v16, v17);
      if ( v6 >= 0 )
      {
        v7 = v17[0];
        v8 = 0;
        if ( v17[0] )
        {
          while ( 1 )
          {
            v6 = (*(__int64 (__fastcall **)(__int64, _QWORD, _QWORD))(*(_QWORD *)v16 + 96LL))(
                   v16,
                   (unsigned int)(v7 - v8 - 1),
                   0);
            if ( v6 < 0 )
              break;
            v7 = v17[0];
            if ( (unsigned int)++v8 >= v17[0] )
              goto LABEL_10;
          }
        }
        else
        {
LABEL_10:
          v6 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, __int64 *))(*(_QWORD *)v16 + 48LL))(
                 v16,
                 L"clear",
                 &v15);
          if ( v6 >= 0 )
          {
            v6 = (*(__int64 (__fastcall **)(__int64, __int64, _QWORD, _QWORD))(*(_QWORD *)v16 + 88LL))(v16, v15, 0, 0);
            if ( v6 >= 0 )
            {
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v15 + 16LL))(v15);
              v15 = 0;
              v9 = (const unsigned __int16 *)*((_QWORD *)BUFFER::QueryPtr((struct PROPERTY_ENTRY *)((char *)a3 + 16)) + 3);
              while ( *v9 )
              {
                STRU::STRU((STRU *)v18);
                v19 = 0;
                v20 = 0;
                v6 = META_ERROR_ENTRY::Parse((META_ERROR_ENTRY *)v18, v9);
                if ( v6 < 0
                  || (v6 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, __int64 *))(*(_QWORD *)v16 + 48LL))(
                             v16,
                             L"error",
                             &v15),
                      v6 < 0)
                  || (v6 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, _QWORD, _QWORD))(*(_QWORD *)v15 + 112LL))(
                             v15,
                             L"statusCode",
                             HIDWORD(v19),
                             0),
                      v6 < 0)
                  || (v6 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, _QWORD, _QWORD))(*(_QWORD *)v15 + 112LL))(
                             v15,
                             L"subStatusCode",
                             (unsigned int)v19,
                             0),
                      v6 < 0)
                  || (v6 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, _QWORD, _QWORD))(*(_QWORD *)v15 + 112LL))(
                             v15,
                             L"responseMode",
                             v20,
                             0),
                      v6 < 0)
                  || (v10 = *(__int64 (__fastcall **)(__int64, const wchar_t *, const unsigned __int16 *, _QWORD))(*(_QWORD *)v15 + 128LL),
                      Str = STRU::QueryStr((STRU *)v18),
                      v6 = v10(v15, L"path", Str, 0),
                      v6 < 0) )
                {
LABEL_27:
                  STRU::~STRU((STRU *)v18);
                  break;
                }
                v12 = (*(__int64 (__fastcall **)(__int64, __int64, __int64, _QWORD))(*(_QWORD *)v16 + 88LL))(
                        v16,
                        v15,
                        0xFFFFFFFFLL,
                        0);
                v6 = v12;
                if ( v12 < 0 )
                {
                  if ( v12 != -2147024713 )
                    goto LABEL_27;
                  v6 = 0;
                }
                (*(void (__fastcall **)(__int64))(*(_QWORD *)v15 + 16LL))(v15);
                v13 = -1;
                v15 = 0;
                do
                  ++v13;
                while ( v9[v13] );
                v9 += v13 + 1;
                STRU::~STRU((STRU *)v18);
              }
            }
          }
        }
      }
    }
  }
  else
  {
    v6 = -2147024809;
  }
  if ( v15 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v15 + 16LL))(v15);
    v15 = 0;
  }
  if ( v16 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v16 + 16LL))(v16);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x180021e80  mov     [rsp-8+arg_0], rbx
0x180021e85  mov     [rsp-8+arg_8], rsi
0x180021e8a  push    rbp
0x180021e8b  push    rdi
0x180021e8c  push    r14
0x180021e8e  lea     rbp, [rsp-3Fh]
0x180021e93  sub     rsp, 0B0h
0x180021e9a  mov     rax, cs:__security_cookie
0x180021ea1  xor     rax, rsp
0x180021ea4  mov     [rbp+4Fh+var_20], rax
0x180021ea8  mov     rcx, [rbp+4Fh+arg_20]
0x180021eac  xor     r14d, r14d
0x180021eaf  mov     [rbp+4Fh+var_88], r14
0x180021eb3  mov     rsi, r8
0x180021eb6  mov     [rbp+4Fh+var_90], r14
0x180021eba  mov     [rbp+4Fh+var_80], r14d
0x180021ebe  test    rdx, rdx
0x180021ec1  jz      loc_180022131
0x180021ec7  test    r8, r8
0x180021eca  jz      loc_180022131
0x180021ed0  test    r9, r9
0x180021ed3  jz      loc_180022131
0x180021ed9  test    rcx, rcx
0x180021edc  jz      loc_180022131
0x180021ee2  mov     rax, [rcx]
0x180021ee5  lea     rdx, [rbp+4Fh+var_88]
0x180021ee9  mov     rax, [rax+28h]
0x180021eed  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021ef2  mov     ebx, eax
0x180021ef4  test    eax, eax
0x180021ef6  js      loc_180022136
0x180021efc  mov     rcx, [rbp+4Fh+var_88]
0x180021f00  lea     rdx, [rbp+4Fh+var_80]
0x180021f04  mov     rax, [rcx]
0x180021f07  mov     rax, [rax+48h]
0x180021f0b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021f10  mov     ebx, eax
0x180021f12  test    eax, eax
0x180021f14  js      loc_180022136
0x180021f1a  mov     edx, [rbp+4Fh+var_80]
0x180021f1d  mov     edi, r14d
0x180021f20  test    edx, edx
0x180021f22  jz      short loc_180021F4E
0x180021f24  mov     rcx, [rbp+4Fh+var_88]
0x180021f28  sub     edx, edi
0x180021f2a  dec     edx
0x180021f2c  xor     r8d, r8d
0x180021f2f  mov     rax, [rcx]
0x180021f32  mov     rax, [rax+60h]
0x180021f36  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021f3b  mov     ebx, eax
0x180021f3d  test    eax, eax
0x180021f3f  js      loc_180022136
0x180021f45  mov     edx, [rbp+4Fh+var_80]
0x180021f48  inc     edi
0x180021f4a  cmp     edi, edx
0x180021f4c  jb      short loc_180021F24
0x180021f4e  mov     rcx, [rbp+4Fh+var_88]
0x180021f52  lea     r8, [rbp+4Fh+var_90]
0x180021f56  lea     rdx, aClear; "clear"
0x180021f5d  mov     rax, [rcx]
0x180021f60  mov     rax, [rax+30h]
0x180021f64  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021f69  mov     ebx, eax
0x180021f6b  test    eax, eax
0x180021f6d  js      loc_180022136
0x180021f73  mov     rcx, [rbp+4Fh+var_88]
0x180021f77  xor     r9d, r9d
0x180021f7a  mov     rdx, [rbp+4Fh+var_90]
0x180021f7e  xor     r8d, r8d
0x180021f81  mov     rax, [rcx]
0x180021f84  mov     rax, [rax+58h]
0x180021f88  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021f8d  mov     ebx, eax
0x180021f8f  test    eax, eax
0x180021f91  js      loc_180022136
0x180021f97  mov     rcx, [rbp+4Fh+var_90]
0x180021f9b  mov     rax, [rcx]
0x180021f9e  mov     rax, [rax+10h]
0x180021fa2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021fa7  lea     rcx, [rsi+10h]
0x180021fab  mov     [rbp+4Fh+var_90], r14
0x180021faf  call    cs:__imp_?QueryPtr@BUFFER@@QEBAPEAXXZ; BUFFER::QueryPtr(void)
0x180021fb5  mov     rdi, [rax+18h]
0x180021fb9  jmp     loc_180022119
0x180021fbe  lea     rcx, [rbp+4Fh+var_70]
0x180021fc2  call    cs:__imp_??0STRU@@QEAA@XZ; STRU::STRU(void)
0x180021fc8  mov     rdx, rdi; unsigned __int16 *
0x180021fcb  mov     [rbp+4Fh+var_38], r14
0x180021fcf  lea     rcx, [rbp+4Fh+var_70]; this
0x180021fd3  mov     [rbp+4Fh+var_30], r14d
0x180021fd7  call    ?Parse@META_ERROR_ENTRY@@QEAAJPEBG@Z; META_ERROR_ENTRY::Parse(ushort const *)
0x180021fdc  mov     ebx, eax
0x180021fde  test    eax, eax
0x180021fe0  js      loc_180022125
0x180021fe6  mov     rcx, [rbp+4Fh+var_88]
0x180021fea  lea     r8, [rbp+4Fh+var_90]
0x180021fee  lea     rdx, aError; "error"
0x180021ff5  mov     rax, [rcx]
0x180021ff8  mov     rax, [rax+30h]
0x180021ffc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022001  mov     ebx, eax
0x180022003  test    eax, eax
0x180022005  js      loc_180022125
0x18002200b  mov     rcx, [rbp+4Fh+var_90]
0x18002200f  lea     rdx, aStatuscode; "statusCode"
0x180022016  mov     r8d, dword ptr [rbp+4Fh+var_38+4]
0x18002201a  xor     r9d, r9d
0x18002201d  mov     rax, [rcx]
0x180022020  mov     rax, [rax+70h]
0x180022024  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022029  mov     ebx, eax
0x18002202b  test    eax, eax
0x18002202d  js      loc_180022125
0x180022033  mov     rcx, [rbp+4Fh+var_90]
0x180022037  lea     rdx, aSubstatuscode; "subStatusCode"
0x18002203e  mov     r8d, dword ptr [rbp+4Fh+var_38]
0x180022042  xor     r9d, r9d
0x180022045  mov     rax, [rcx]
0x180022048  mov     rax, [rax+70h]
0x18002204c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022051  mov     ebx, eax
0x180022053  test    eax, eax
0x180022055  js      loc_180022125
0x18002205b  mov     rcx, [rbp+4Fh+var_90]
0x18002205f  lea     rdx, aResponsemode; "responseMode"
0x180022066  mov     r8d, [rbp+4Fh+var_30]
0x18002206a  xor     r9d, r9d
0x18002206d  mov     rax, [rcx]
0x180022070  mov     rax, [rax+70h]
0x180022074  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022079  mov     ebx, eax
0x18002207b  test    eax, eax
0x18002207d  js      loc_180022125
0x180022083  mov     rax, [rbp+4Fh+var_90]
0x180022087  mov     rcx, [rax]
0x18002208a  mov     rbx, [rcx+80h]
0x180022091  lea     rcx, [rbp+4Fh+var_70]
0x180022095  call    cs:__imp_?QueryStr@STRU@@QEBAPEBGXZ; STRU::QueryStr(void)
0x18002209b  mov     rcx, [rbp+4Fh+var_90]
0x18002209f  lea     rdx, aPath; "path"
0x1800220a6  mov     r8, rax
0x1800220a9  xor     r9d, r9d
0x1800220ac  mov     rax, rbx
0x1800220af  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800220b4  mov     ebx, eax
0x1800220b6  test    eax, eax
0x1800220b8  js      short loc_180022125
0x1800220ba  mov     rcx, [rbp+4Fh+var_88]
0x1800220be  xor     r9d, r9d
0x1800220c1  mov     rdx, [rbp+4Fh+var_90]
0x1800220c5  or      r8d, 0FFFFFFFFh
0x1800220c9  mov     rax, [rcx]
0x1800220cc  mov     rax, [rax+58h]
0x1800220d0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800220d5  mov     ebx, eax
0x1800220d7  test    eax, eax
0x1800220d9  jns     short loc_1800220E5
0x1800220db  cmp     eax, 800700B7h
0x1800220e0  jnz     short loc_180022125
0x1800220e2  mov     ebx, r14d
0x1800220e5  mov     rcx, [rbp+4Fh+var_90]
0x1800220e9  mov     rax, [rcx]
0x1800220ec  mov     rax, [rax+10h]
0x1800220f0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800220f5  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800220f9  mov     [rbp+4Fh+var_90], r14
0x1800220fd  inc     rax
0x180022100  cmp     [rdi+rax*2], r14w
0x180022105  jnz     short loc_1800220FD
0x180022107  lea     rdi, [rdi+rax*2]
0x18002210b  add     rdi, 2
0x18002210f  lea     rcx, [rbp+4Fh+var_70]
0x180022113  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x180022119  cmp     [rdi], r14w
0x18002211d  jnz     loc_180021FBE
0x180022123  jmp     short loc_180022136
0x180022125  lea     rcx, [rbp+4Fh+var_70]
0x180022129  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x18002212f  jmp     short loc_180022136
0x180022131  mov     ebx, 80070057h
0x180022136  mov     rcx, [rbp+4Fh+var_90]
0x18002213a  test    rcx, rcx
0x18002213d  jz      short loc_18002214F
0x18002213f  mov     rax, [rcx]
0x180022142  mov     rax, [rax+10h]
0x180022146  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002214b  mov     [rbp+4Fh+var_90], r14
0x18002214f  mov     rcx, [rbp+4Fh+var_88]
0x180022153  test    rcx, rcx
0x180022156  jz      short loc_180022164
0x180022158  mov     rax, [rcx]
0x18002215b  mov     rax, [rax+10h]
0x18002215f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022164  mov     eax, ebx
0x180022166  mov     rcx, [rbp+4Fh+var_20]
0x18002216a  xor     rcx, rsp; StackCookie
0x18002216d  call    __security_check_cookie
0x180022172  lea     r11, [rsp+0C0h+var_10]
0x18002217a  mov     rbx, [r11+20h]
0x18002217e  mov     rsi, [r11+28h]
0x180022182  mov     rsp, r11
0x180022185  pop     r14
0x180022187  pop     rdi
0x180022188  pop     rbp
0x180022189  retn
```
