# REQUEST_OBJECT::Create(void)

- ea: `0x18001ed98`
- end: `0x18001f10e`
- name: `?Create@REQUEST_OBJECT@@QEAAJXZ`
- size: `886`
- prototype: `__int64 __fastcall(REQUEST_OBJECT *__hidden this)`
- caller_count: `1`
- callee_count: `10`
- tags: `file_ops, service_task, broker_com_uri`

## callers

- `0x18001f120`

## callees

- `0x180001fb0`
- `0x180002e90`
- `0x180004a70`
- `0x180005ba8`
- `0x18000d654`
- `0x18001ed98`
- `0x18001fcb4`
- `0x180034cbe`
- `0x180034d00`
- `0x180036010`

## import_xrefs

- `msvcrt!_ultow` at `0x18001f0a2`
- `msvcrt!_ultow` at `0x18001f0a2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001f0c7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001f0c7`

## pseudocode

```c
__int64 __fastcall REQUEST_OBJECT::Create(REQUEST_OBJECT *this)
{
  unsigned __int16 *v2; // rsi
  __int64 *v3; // rcx
  __int64 v4; // rax
  int v5; // ebx
  REQUEST_OBJECT *v6; // rcx
  unsigned int v8; // [rsp+20h] [rbp-E0h] BYREF
  unsigned int v9; // [rsp+24h] [rbp-DCh] BYREF
  unsigned int Value; // [rsp+28h] [rbp-D8h] BYREF
  LPVOID pv; // [rsp+30h] [rbp-D0h] BYREF
  unsigned __int16 *v12; // [rsp+38h] [rbp-C8h] BYREF
  unsigned __int16 *v13; // [rsp+40h] [rbp-C0h] BYREF
  unsigned __int16 *v14; // [rsp+48h] [rbp-B8h] BYREF
  unsigned __int16 *v15; // [rsp+50h] [rbp-B0h] BYREF
  unsigned __int16 *v16; // [rsp+58h] [rbp-A8h] BYREF
  _BYTE v17[32]; // [rsp+60h] [rbp-A0h] BYREF
  unsigned __int16 *v18; // [rsp+80h] [rbp-80h]
  int v19; // [rsp+88h] [rbp-78h]
  __int16 v20; // [rsp+8Ch] [rbp-74h]
  int v21; // [rsp+90h] [rbp-70h]
  _BYTE v22[32]; // [rsp+98h] [rbp-68h] BYREF
  unsigned __int16 *v23; // [rsp+B8h] [rbp-48h]
  int v24; // [rsp+C0h] [rbp-40h]
  __int16 v25; // [rsp+C4h] [rbp-3Ch]
  int v26; // [rsp+C8h] [rbp-38h]
  unsigned __int16 v27; // [rsp+D0h] [rbp-30h] BYREF
  _BYTE v28[126]; // [rsp+D2h] [rbp-2Eh] BYREF
  wchar_t Buffer[64]; // [rsp+150h] [rbp+50h] BYREF
  __int16 v30; // [rsp+1D0h] [rbp+D0h] BYREF
  _BYTE v31[510]; // [rsp+1D2h] [rbp+D2h] BYREF

  pv = 0;
  Value = 0;
  memset_0(v31, 0, sizeof(v31));
  v24 = 512;
  v2 = L"Unknown";
  v23 = (unsigned __int16 *)&v30;
  v25 = 256;
  v26 = 0;
  v30 = 0;
  v12 = 0;
  v13 = 0;
  v14 = 0;
  v15 = L"Unknown";
  v16 = L"Unknown";
  v8 = 0;
  memset_0(v28, 0, sizeof(v28));
  v3 = (__int64 *)*((_QWORD *)this + 27);
  v18 = &v27;
  v27 = 0;
  v9 = 0;
  v4 = *v3;
  v19 = 128;
  v20 = 256;
  v21 = 0;
  v5 = (*(__int64 (__fastcall **)(__int64 *, LPVOID *))(v4 + 24))(v3, &pv);
  if ( v5 >= 0 )
  {
    v5 = COMMAND_OBJECT::AddAttribute(this, L"REQUEST.NAME", (const unsigned __int16 *)pv);
    if ( v5 >= 0 )
    {
      v5 = (*(__int64 (__fastcall **)(_QWORD, unsigned __int16 **))(**((_QWORD **)this + 27) + 48LL))(
             *((_QWORD *)this + 27),
             &v12);
      if ( v5 >= 0 )
      {
        v5 = COMMAND_OBJECT::AddAttribute(this, L"Url", v12);
        if ( v5 >= 0 )
        {
          v5 = (*(__int64 (__fastcall **)(_QWORD, unsigned __int16 **))(**((_QWORD **)this + 27) + 40LL))(
                 *((_QWORD *)this + 27),
                 &v13);
          if ( v5 >= 0 )
          {
            v5 = COMMAND_OBJECT::AddAttribute(this, L"Verb", v13);
            if ( v5 >= 0 )
            {
              v5 = (*(__int64 (__fastcall **)(_QWORD, unsigned __int16 **))(**((_QWORD **)this + 27) + 80LL))(
                     *((_QWORD *)this + 27),
                     &v14);
              if ( v5 >= 0 )
              {
                v5 = COMMAND_OBJECT::AddAttribute(this, L"ClientIp", v14);
                if ( v5 >= 0 )
                {
                  if ( (*(int (__fastcall **)(_QWORD, unsigned int *))(**((_QWORD **)this + 27) + 96LL))(
                         *((_QWORD *)this + 27),
                         &v8) >= 0 )
                  {
                    REQUEST_OBJECT::TranslateRequestStageToString(v6, v8, (const unsigned __int16 **)&v15);
                    v2 = v15;
                  }
                  v5 = COMMAND_OBJECT::AddAttribute(this, L"Stage", v2);
                  if ( v5 >= 0 )
                  {
                    (*(void (__fastcall **)(_QWORD, unsigned __int16 **))(**((_QWORD **)this + 27) + 112LL))(
                      *((_QWORD *)this + 27),
                      &v16);
                    v5 = COMMAND_OBJECT::AddAttribute(this, L"Module", v16);
                    if ( v5 >= 0 )
                    {
                      v5 = (*(__int64 (__fastcall **)(_QWORD, unsigned int *))(**((_QWORD **)this + 27) + 88LL))(
                             *((_QWORD *)this + 27),
                             &v9);
                      if ( v5 >= 0 )
                      {
                        v5 = StringCchPrintfW(&v27, 0x40u, L"%d", v9);
                        if ( v5 >= 0 )
                        {
                          STRU::SyncWithBuffer((STRU *)v17);
                          v5 = COMMAND_OBJECT::AddAttribute(this, L"Time", v18);
                          if ( v5 >= 0 )
                          {
                            v5 = STRU::Copy((STRU *)v22, (const unsigned __int8 *)pv);
                            if ( v5 >= 0 )
                            {
                              v5 = STRU::Copy((REQUEST_OBJECT *)((char *)this + 16), (const unsigned __int8 *)v23);
                              if ( v5 >= 0 )
                              {
                                v5 = (*(__int64 (__fastcall **)(_QWORD, unsigned int *))(**((_QWORD **)this + 27) + 56LL))(
                                       *((_QWORD *)this + 27),
                                       &Value);
                                if ( v5 >= 0 )
                                {
                                  _ultow(Value, Buffer, 10);
                                  v5 = COMMAND_OBJECT::AddAttribute(this, L"SITE.ID", Buffer);
                                }
                              }
                            }
                          }
                        }
                      }
                    }
                  }
                }
              }
            }
          }
        }
      }
    }
  }
  if ( pv )
  {
    CoTaskMemFree(pv);
    pv = 0;
  }
  BUFFER::~BUFFER((BUFFER *)v17);
  BUFFER::~BUFFER((BUFFER *)v22);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x18001ed98  mov     [rsp-8+arg_8], rbx
0x18001ed9d  mov     [rsp-8+arg_10], rsi
0x18001eda2  push    rbp
0x18001eda3  push    rdi
0x18001eda4  push    r14
0x18001eda6  lea     rbp, [rsp-2E0h]
0x18001edae  sub     rsp, 3E0h
0x18001edb5  mov     rax, cs:__security_cookie
0x18001edbc  xor     rax, rsp
0x18001edbf  mov     [rbp+2F0h+var_20], rax
0x18001edc6  mov     rdi, rcx
0x18001edc9  xor     r14d, r14d
0x18001edcc  lea     rcx, [rbp+2F0h+var_21E]; void *
0x18001edd3  mov     [rsp+3F0h+pv], r14
0x18001edd8  xor     edx, edx; Val
0x18001edda  mov     [rsp+3F0h+Value], r14d
0x18001eddf  mov     r8d, 1FEh; Size
0x18001ede5  call    memset_0
0x18001edea  lea     rax, [rbp+2F0h+var_220]
0x18001edf1  mov     [rbp+2F0h+var_330], 200h
0x18001edf8  lea     rsi, aUnknown_0; "Unknown"
0x18001edff  mov     [rbp+2F0h+var_338], rax
0x18001ee03  xor     edx, edx; Val
0x18001ee05  mov     [rbp+2F0h+var_32C], 100h
0x18001ee0b  lea     r8d, [r14+7Eh]; Size
0x18001ee0f  mov     [rbp+2F0h+var_328], r14d
0x18001ee13  lea     rcx, [rbp+2F0h+var_31E]; void *
0x18001ee17  mov     [rbp+2F0h+var_220], r14w
0x18001ee1f  mov     [rsp+3F0h+var_3B8], r14
0x18001ee24  mov     [rsp+3F0h+var_3B0], r14
0x18001ee29  mov     [rsp+3F0h+var_3A8], r14
0x18001ee2e  mov     [rsp+3F0h+var_3A0], rsi
0x18001ee33  mov     [rsp+3F0h+var_398], rsi
0x18001ee38  mov     [rsp+3F0h+var_3D0], r14d
0x18001ee3d  call    memset_0
0x18001ee42  mov     rcx, [rdi+0D8h]
0x18001ee49  lea     rax, [rbp+2F0h+var_320]
0x18001ee4d  mov     [rbp+2F0h+var_370], rax
0x18001ee51  lea     rdx, [rsp+3F0h+pv]
0x18001ee56  mov     [rbp+2F0h+var_320], r14w
0x18001ee5b  mov     [rsp+3F0h+var_3CC], r14d
0x18001ee60  mov     rax, [rcx]
0x18001ee63  mov     [rbp+2F0h+var_368], 80h
0x18001ee6a  mov     [rbp+2F0h+var_364], 100h
0x18001ee70  mov     [rbp+2F0h+var_360], r14d
0x18001ee74  mov     rax, [rax+18h]
0x18001ee78  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ee7d  mov     ebx, eax
0x18001ee7f  test    eax, eax
0x18001ee81  js      loc_18001F0BD
0x18001ee87  mov     r8, [rsp+3F0h+pv]; unsigned __int16 *
0x18001ee8c  lea     rdx, aRequestName; "REQUEST.NAME"
0x18001ee93  mov     rcx, rdi; this
0x18001ee96  call    ?AddAttribute@COMMAND_OBJECT@@QEAAJPEBG0@Z; COMMAND_OBJECT::AddAttribute(ushort const *,ushort const *)
0x18001ee9b  mov     ebx, eax
0x18001ee9d  test    eax, eax
0x18001ee9f  js      loc_18001F0BD
0x18001eea5  mov     rcx, [rdi+0D8h]
0x18001eeac  lea     rdx, [rsp+3F0h+var_3B8]
0x18001eeb1  mov     rax, [rcx]
0x18001eeb4  mov     rax, [rax+30h]
0x18001eeb8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001eebd  mov     ebx, eax
0x18001eebf  test    eax, eax
0x18001eec1  js      loc_18001F0BD
0x18001eec7  mov     r8, [rsp+3F0h+var_3B8]; unsigned __int16 *
0x18001eecc  lea     rdx, aUrl_0; "Url"
0x18001eed3  mov     rcx, rdi; this
0x18001eed6  call    ?AddAttribute@COMMAND_OBJECT@@QEAAJPEBG0@Z; COMMAND_OBJECT::AddAttribute(ushort const *,ushort const *)
0x18001eedb  mov     ebx, eax
0x18001eedd  test    eax, eax
0x18001eedf  js      loc_18001F0BD
0x18001eee5  mov     rcx, [rdi+0D8h]
0x18001eeec  lea     rdx, [rsp+3F0h+var_3B0]
0x18001eef1  mov     rax, [rcx]
0x18001eef4  mov     rax, [rax+28h]
0x18001eef8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001eefd  mov     ebx, eax
0x18001eeff  test    eax, eax
0x18001ef01  js      loc_18001F0BD
0x18001ef07  mov     r8, [rsp+3F0h+var_3B0]; unsigned __int16 *
0x18001ef0c  lea     rdx, aVerb_0; "Verb"
0x18001ef13  mov     rcx, rdi; this
0x18001ef16  call    ?AddAttribute@COMMAND_OBJECT@@QEAAJPEBG0@Z; COMMAND_OBJECT::AddAttribute(ushort const *,ushort const *)
0x18001ef1b  mov     ebx, eax
0x18001ef1d  test    eax, eax
0x18001ef1f  js      loc_18001F0BD
0x18001ef25  mov     rcx, [rdi+0D8h]
0x18001ef2c  lea     rdx, [rsp+3F0h+var_3A8]
0x18001ef31  mov     rax, [rcx]
0x18001ef34  mov     rax, [rax+50h]
0x18001ef38  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ef3d  mov     ebx, eax
0x18001ef3f  test    eax, eax
0x18001ef41  js      loc_18001F0BD
0x18001ef47  mov     r8, [rsp+3F0h+var_3A8]; unsigned __int16 *
0x18001ef4c  lea     rdx, aClientip; "ClientIp"
0x18001ef53  mov     rcx, rdi; this
0x18001ef56  call    ?AddAttribute@COMMAND_OBJECT@@QEAAJPEBG0@Z; COMMAND_OBJECT::AddAttribute(ushort const *,ushort const *)
0x18001ef5b  mov     ebx, eax
0x18001ef5d  test    eax, eax
0x18001ef5f  js      loc_18001F0BD
0x18001ef65  mov     rcx, [rdi+0D8h]
0x18001ef6c  lea     rdx, [rsp+3F0h+var_3D0]
0x18001ef71  mov     rax, [rcx]
0x18001ef74  mov     rax, [rax+60h]
0x18001ef78  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ef7d  test    eax, eax
0x18001ef7f  js      short loc_18001EF94
0x18001ef81  mov     edx, [rsp+3F0h+var_3D0]; unsigned int
0x18001ef85  lea     r8, [rsp+3F0h+var_3A0]; unsigned __int16 **
0x18001ef8a  call    ?TranslateRequestStageToString@REQUEST_OBJECT@@AEAAJKPEAPEBG@Z; REQUEST_OBJECT::TranslateRequestStageToString(ulong,ushort const * *)
0x18001ef8f  mov     rsi, [rsp+3F0h+var_3A0]
0x18001ef94  mov     r8, rsi; unsigned __int16 *
0x18001ef97  lea     rdx, aStage; "Stage"
0x18001ef9e  mov     rcx, rdi; this
0x18001efa1  call    ?AddAttribute@COMMAND_OBJECT@@QEAAJPEBG0@Z; COMMAND_OBJECT::AddAttribute(ushort const *,ushort const *)
0x18001efa6  mov     ebx, eax
0x18001efa8  test    eax, eax
0x18001efaa  js      loc_18001F0BD
0x18001efb0  mov     rcx, [rdi+0D8h]
0x18001efb7  lea     rdx, [rsp+3F0h+var_398]
0x18001efbc  mov     rax, [rcx]
0x18001efbf  mov     rax, [rax+70h]
0x18001efc3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001efc8  mov     r8, [rsp+3F0h+var_398]; unsigned __int16 *
0x18001efcd  lea     rdx, aModule; "Module"
0x18001efd4  mov     rcx, rdi; this
0x18001efd7  call    ?AddAttribute@COMMAND_OBJECT@@QEAAJPEBG0@Z; COMMAND_OBJECT::AddAttribute(ushort const *,ushort const *)
0x18001efdc  mov     ebx, eax
0x18001efde  test    eax, eax
0x18001efe0  js      loc_18001F0BD
0x18001efe6  mov     rcx, [rdi+0D8h]
0x18001efed  lea     rdx, [rsp+3F0h+var_3CC]
0x18001eff2  mov     rax, [rcx]
0x18001eff5  mov     rax, [rax+58h]
0x18001eff9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001effe  mov     ebx, eax
0x18001f000  test    eax, eax
0x18001f002  js      loc_18001F0BD
0x18001f008  mov     r9d, [rsp+3F0h+var_3CC]
0x18001f00d  lea     r8, aD; "%d"
0x18001f014  mov     edx, 40h ; '@'; unsigned __int64
0x18001f019  lea     rcx, [rbp+2F0h+var_320]; unsigned __int16 *
0x18001f01d  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18001f022  mov     ebx, eax
0x18001f024  test    eax, eax
0x18001f026  js      loc_18001F0BD
0x18001f02c  lea     rcx, [rsp+3F0h+var_390]; this
0x18001f031  call    ?SyncWithBuffer@STRU@@QEAAXXZ; STRU::SyncWithBuffer(void)
0x18001f036  mov     r8, [rbp+2F0h+var_370]; unsigned __int16 *
0x18001f03a  lea     rdx, aTime; "Time"
0x18001f041  mov     rcx, rdi; this
0x18001f044  call    ?AddAttribute@COMMAND_OBJECT@@QEAAJPEBG0@Z; COMMAND_OBJECT::AddAttribute(ushort const *,ushort const *)
0x18001f049  mov     ebx, eax
0x18001f04b  test    eax, eax
0x18001f04d  js      short loc_18001F0BD
0x18001f04f  mov     rdx, [rsp+3F0h+pv]; unsigned __int16 *
0x18001f054  lea     rcx, [rbp+2F0h+var_358]; this
0x18001f058  call    ?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x18001f05d  mov     ebx, eax
0x18001f05f  test    eax, eax
0x18001f061  js      short loc_18001F0BD
0x18001f063  mov     rdx, [rbp+2F0h+var_338]; unsigned __int16 *
0x18001f067  lea     rcx, [rdi+10h]; this
0x18001f06b  call    ?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x18001f070  mov     ebx, eax
0x18001f072  test    eax, eax
0x18001f074  js      short loc_18001F0BD
0x18001f076  mov     rcx, [rdi+0D8h]
0x18001f07d  lea     rdx, [rsp+3F0h+Value]
0x18001f082  mov     rax, [rcx]
0x18001f085  mov     rax, [rax+38h]
0x18001f089  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f08e  mov     ebx, eax
0x18001f090  test    eax, eax
0x18001f092  js      short loc_18001F0BD
0x18001f094  mov     ecx, [rsp+3F0h+Value]; Value
0x18001f098  lea     rdx, [rbp+2F0h+Buffer]; Buffer
0x18001f09c  mov     r8d, 0Ah; Radix
0x18001f0a2  call    cs:__imp__ultow
0x18001f0a8  lea     r8, [rbp+2F0h+Buffer]; unsigned __int16 *
0x18001f0ac  mov     rcx, rdi; this
0x18001f0af  lea     rdx, aSiteId; "SITE.ID"
0x18001f0b6  call    ?AddAttribute@COMMAND_OBJECT@@QEAAJPEBG0@Z; COMMAND_OBJECT::AddAttribute(ushort const *,ushort const *)
0x18001f0bb  mov     ebx, eax
0x18001f0bd  mov     rcx, [rsp+3F0h+pv]; pv
0x18001f0c2  test    rcx, rcx
0x18001f0c5  jz      short loc_18001F0D2
0x18001f0c7  call    cs:__imp_CoTaskMemFree
0x18001f0cd  mov     [rsp+3F0h+pv], r14
0x18001f0d2  lea     rcx, [rsp+3F0h+var_390]; this
0x18001f0d7  call    ??1BUFFER@@QEAA@XZ; BUFFER::~BUFFER(void)
0x18001f0dc  lea     rcx, [rbp+2F0h+var_358]; this
0x18001f0e0  call    ??1BUFFER@@QEAA@XZ; BUFFER::~BUFFER(void)
0x18001f0e5  mov     eax, ebx
0x18001f0e7  mov     rcx, [rbp+2F0h+var_20]
0x18001f0ee  xor     rcx, rsp; StackCookie
0x18001f0f1  call    __security_check_cookie
0x18001f0f6  lea     r11, [rsp+3F0h+var_10]
0x18001f0fe  mov     rbx, [r11+28h]
0x18001f102  mov     rsi, [r11+30h]
0x18001f106  mov     rsp, r11
0x18001f109  pop     r14
0x18001f10b  pop     rdi
0x18001f10c  pop     rbp
0x18001f10d  retn
```
