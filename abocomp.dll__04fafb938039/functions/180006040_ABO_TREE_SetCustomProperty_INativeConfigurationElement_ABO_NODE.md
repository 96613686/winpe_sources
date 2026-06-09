# ABO_TREE::SetCustomProperty(INativeConfigurationElement *,ABO_NODE *)

- ea: `0x180006040`
- end: `0x18000641d`
- name: `?SetCustomProperty@ABO_TREE@@AEAAJPEAVINativeConfigurationElement@@PEAVABO_NODE@@@Z`
- size: `989`
- prototype: `__int64 __fastcall(ABO_TREE *__hidden this, struct INativeConfigurationElement *, struct ABO_NODE *)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, registry_config`

## callers

- `0x180004828`

## callees

- `0x18000341a`
- `0x180003460`
- `0x180006040`
- `0x18000a6fc`
- `0x18002c010`

## import_xrefs

- `msvcrt!wcstoul` at `0x18000621e`
- `msvcrt!wcstoul` at `0x18000621e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800062da`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800062da`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x180006361`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x180006361`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x1800060c5`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x1800060c5`
- `iisutil!??1BUFFER@@QEAA@XZ` at `0x1800063d0`
- `iisutil!??1BUFFER@@QEAA@XZ` at `0x1800063d0`
- `iisutil!??0BUFFER@@QEAA@PEAEK@Z` at `0x1800060f8`
- `iisutil!??0BUFFER@@QEAA@PEAEK@Z` at `0x1800060f8`
- `iisutil!??1STRU@@QEAA@XZ` at `0x1800063e4`
- `iisutil!??1STRU@@QEAA@XZ` at `0x1800063e4`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x18000629f`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x18000629f`
- `iisutil!?Copy@STRU@@QEAAJPEBGK@Z` at `0x18000628b`
- `iisutil!?Copy@STRU@@QEAAJPEBGK@Z` at `0x18000628b`
- `iisutil!??0MULTISZ@@QEAA@XZ` at `0x180006098`
- `iisutil!??0MULTISZ@@QEAA@XZ` at `0x180006098`
- `iisutil!?QueryStr@MULTISZ@@QEBAPEAGXZ` at `0x1800062fd`
- `iisutil!?QueryStr@MULTISZ@@QEBAPEAGXZ` at `0x1800062fd`
- `iisutil!??0STRA@@QEAA@PEADK@Z` at `0x1800060d9`
- `iisutil!??0STRA@@QEAA@PEADK@Z` at `0x1800060d9`
- `iisutil!?Append@MULTISZ@@QEAAHPEBG@Z` at `0x1800062ad`
- `iisutil!?Append@MULTISZ@@QEAAHPEBG@Z` at `0x1800062d0`
- `iisutil!?Append@MULTISZ@@QEAAHPEBG@Z` at `0x1800062ad`
- `iisutil!?Append@MULTISZ@@QEAAHPEBG@Z` at `0x1800062d0`
- `iisutil!?QueryCB@MULTISZ@@QEBAIXZ` at `0x18000630b`
- `iisutil!?QueryCB@MULTISZ@@QEBAIXZ` at `0x18000630b`
- `iisutil!?CopyW@STRA@@QEAAJPEBG@Z` at `0x180006323`
- `iisutil!?CopyW@STRA@@QEAAJPEBG@Z` at `0x180006323`
- `iisutil!?QueryStr@STRA@@QEAAPEADXZ` at `0x180006337`
- `iisutil!?QueryStr@STRA@@QEAAPEADXZ` at `0x180006337`
- `iisutil!uudecode` at `0x18000634c`
- `iisutil!uudecode` at `0x18000634c`
- `iisutil!??1STRA@@QEAA@XZ` at `0x1800063da`
- `iisutil!??1STRA@@QEAA@XZ` at `0x1800063da`
- `iisutil!??1MULTISZ@@QEAA@XZ` at `0x1800063ef`
- `iisutil!??1MULTISZ@@QEAA@XZ` at `0x1800063ef`

## pseudocode

```c
__int64 __fastcall ABO_TREE::SetCustomProperty(
        ABO_TREE *this,
        struct INativeConfigurationElement *a2,
        struct ABO_NODE *a3)
{
  __int64 v5; // rax
  signed int v6; // ebx
  DWORD v7; // ecx
  wchar_t *v8; // rbx
  DWORD CB; // edx
  wchar_t *v10; // rdi
  wchar_t v11; // ax
  const unsigned __int16 *v12; // rdx
  const unsigned __int16 *v13; // rax
  signed int LastError; // eax
  char *Str; // rax
  wchar_t *Ptr; // rax
  __int64 v17; // rax
  DWORD v19; // [rsp+30h] [rbp-D0h] BYREF
  unsigned int v20; // [rsp+34h] [rbp-CCh] BYREF
  DWORD v21; // [rsp+38h] [rbp-C8h] BYREF
  DWORD v22; // [rsp+3Ch] [rbp-C4h] BYREF
  DWORD v23; // [rsp+40h] [rbp-C0h] BYREF
  DWORD v24; // [rsp+44h] [rbp-BCh] BYREF
  wchar_t *String; // [rsp+48h] [rbp-B8h] BYREF
  struct _METADATA_RECORD v26; // [rsp+50h] [rbp-B0h] BYREF
  _BYTE v27[56]; // [rsp+78h] [rbp-88h] BYREF
  _BYTE v28[48]; // [rsp+B0h] [rbp-50h] BYREF
  _BYTE v29[56]; // [rsp+E0h] [rbp-20h] BYREF
  _BYTE v30[56]; // [rsp+118h] [rbp+18h] BYREF
  unsigned __int8 v31[256]; // [rsp+150h] [rbp+50h] BYREF
  char v32[256]; // [rsp+250h] [rbp+150h] BYREF
  unsigned __int16 v33[256]; // [rsp+350h] [rbp+250h] BYREF

  v22 = 0;
  v24 = 0;
  v19 = 0;
  v23 = 0;
  String = 0;
  v20 = 0;
  MULTISZ::MULTISZ((MULTISZ *)v27);
  memset_0(v33, 0, sizeof(v33));
  STRU::STRU((STRU *)v30, v33, 0x100u);
  STRA::STRA((STRA *)v29, v32, 0x100u);
  memset_0(v31, 0, sizeof(v31));
  BUFFER::BUFFER((BUFFER *)v28, v31, 0x100u);
  v21 = 0;
  if ( !a2 || !a3 )
  {
    v6 = -2147024809;
    goto LABEL_39;
  }
  v5 = *(_QWORD *)a2;
  memset(&v26, 0, sizeof(v26));
  v6 = (*(__int64 (__fastcall **)(struct INativeConfigurationElement *, const wchar_t *, DWORD *, _QWORD, _QWORD))(v5 + 48))(
         a2,
         L"id",
         &v22,
         0,
         0);
  if ( v6 >= 0 )
  {
    v6 = (*(__int64 (__fastcall **)(struct INativeConfigurationElement *, const wchar_t *, DWORD *, _QWORD, _QWORD))(*(_QWORD *)a2 + 48LL))(
           a2,
           L"dataType",
           &v19,
           0,
           0);
    if ( v6 >= 0 )
    {
      v6 = (*(__int64 (__fastcall **)(struct INativeConfigurationElement *, const wchar_t *, DWORD *, _QWORD, _QWORD))(*(_QWORD *)a2 + 48LL))(
             a2,
             L"userType",
             &v23,
             0,
             0);
      if ( v6 >= 0 )
      {
        v6 = (*(__int64 (__fastcall **)(struct INativeConfigurationElement *, const wchar_t *, DWORD *, _QWORD, _QWORD))(*(_QWORD *)a2 + 48LL))(
               a2,
               L"attributes",
               &v24,
               0,
               0);
        if ( v6 >= 0 )
        {
          v6 = (*(__int64 (__fastcall **)(struct INativeConfigurationElement *, const wchar_t *, wchar_t **, _QWORD, _QWORD))(*(_QWORD *)a2 + 64LL))(
                 a2,
                 L"value",
                 &String,
                 0,
                 0);
          if ( v6 >= 0 )
          {
            v7 = v19;
            if ( v19 == 1 )
            {
              v20 = wcstoul(String, 0, 10);
              v8 = (wchar_t *)&v20;
              CB = 4;
LABEL_33:
              v7 = v19;
LABEL_37:
              v26.dwMDIdentifier = v22;
              v26.dwMDUserType = v23;
              v26.dwMDDataType = v7;
              v26.dwMDDataLen = CB;
              v26.dwMDAttributes = v24;
              v26.pbMDData = (unsigned __int8 *)v8;
              v6 = ABO_NODE::SetData(a3, &v26, 0);
              goto LABEL_39;
            }
            if ( ((v19 - 2) & 0xFFFFFFFD) == 0 )
            {
              v8 = String;
              v17 = -1;
              do
                ++v17;
              while ( String[v17] );
              CB = 2 * v17 + 2;
              goto LABEL_37;
            }
            if ( v19 != 5 )
            {
              if ( v19 == 3 )
              {
                v6 = STRA::CopyW((STRA *)v29, String);
                if ( v6 < 0 )
                  goto LABEL_39;
                Str = STRA::QueryStr((STRA *)v29);
                if ( uudecode(Str, (struct BUFFER *)v28, &v21, 0) )
                {
                  Ptr = (wchar_t *)BUFFER::QueryPtr((BUFFER *)v28);
                  CB = v21;
                  v8 = Ptr;
                  goto LABEL_33;
                }
              }
              v6 = -2147024883;
              goto LABEL_39;
            }
            v10 = String;
            v11 = *String;
            if ( !*String )
            {
LABEL_27:
              v8 = MULTISZ::QueryStr((MULTISZ *)v27);
              CB = MULTISZ::QueryCB((MULTISZ *)v27);
              goto LABEL_33;
            }
            v12 = 0;
            do
            {
              if ( v11 == 13 || v11 == 10 )
              {
                if ( v12 )
                {
                  v6 = STRU::Copy((STRU *)v30, v12, v10 - v12);
                  if ( v6 < 0 )
                    goto LABEL_39;
                  v13 = STRU::QueryStr((STRU *)v30);
                  if ( !MULTISZ::Append((MULTISZ *)v27, v13) )
                    goto LABEL_25;
                  v12 = 0;
                }
              }
              else if ( !v12 )
              {
                v12 = v10;
              }
              v11 = *++v10;
            }
            while ( *v10 );
            if ( !v12 || MULTISZ::Append((MULTISZ *)v27, v12) )
              goto LABEL_27;
LABEL_25:
            LastError = GetLastError();
            v6 = LastError;
            if ( LastError > 0 )
              v6 = (unsigned __int16)LastError | 0x80070000;
          }
        }
      }
    }
  }
LABEL_39:
  BUFFER::~BUFFER((BUFFER *)v28);
  STRA::~STRA((STRA *)v29);
  STRU::~STRU((STRU *)v30);
  MULTISZ::~MULTISZ((MULTISZ *)v27);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x180006040  mov     [rsp-8+arg_0], rbx
0x180006045  push    rbp
0x180006046  push    rsi
0x180006047  push    rdi
0x180006048  push    r14
0x18000604a  push    r15
0x18000604c  lea     rbp, [rsp-460h]
0x180006054  sub     rsp, 560h
0x18000605b  mov     rax, cs:__security_cookie
0x180006062  xor     rax, rsp
0x180006065  mov     [rbp+480h+var_30], rax
0x18000606c  xor     r15d, r15d
0x18000606f  lea     rcx, [rsp+580h+var_508]
0x180006074  mov     [rsp+580h+var_544], r15d
0x180006079  mov     r14, r8
0x18000607c  mov     [rsp+580h+var_53C], r15d
0x180006081  mov     rdi, rdx
0x180006084  mov     [rsp+580h+var_550], r15d
0x180006089  mov     [rsp+580h+var_540], r15d
0x18000608e  mov     [rsp+580h+String], r15
0x180006093  mov     [rsp+580h+var_54C], r15d
0x180006098  call    cs:__imp_??0MULTISZ@@QEAA@XZ; MULTISZ::MULTISZ(void)
0x18000609e  xor     edx, edx; Val
0x1800060a0  lea     rcx, [rbp+480h+var_230]; void *
0x1800060a7  mov     r8d, 200h; Size
0x1800060ad  call    memset_0
0x1800060b2  mov     ebx, 100h
0x1800060b7  lea     rdx, [rbp+480h+var_230]
0x1800060be  mov     r8d, ebx
0x1800060c1  lea     rcx, [rbp+480h+var_468]
0x1800060c5  call    cs:__imp_??0STRU@@QEAA@PEAGK@Z; STRU::STRU(ushort *,ulong)
0x1800060cb  mov     r8d, ebx
0x1800060ce  lea     rdx, [rbp+480h+var_330]
0x1800060d5  lea     rcx, [rbp+480h+var_4A0]
0x1800060d9  call    cs:__imp_??0STRA@@QEAA@PEADK@Z; STRA::STRA(char *,ulong)
0x1800060df  mov     r8d, ebx; Size
0x1800060e2  lea     rcx, [rbp+480h+var_430]; void *
0x1800060e6  xor     edx, edx; Val
0x1800060e8  call    memset_0
0x1800060ed  mov     r8d, ebx
0x1800060f0  lea     rdx, [rbp+480h+var_430]
0x1800060f4  lea     rcx, [rbp+480h+var_4D0]
0x1800060f8  call    cs:__imp_??0BUFFER@@QEAA@PEAEK@Z; BUFFER::BUFFER(uchar *,ulong)
0x1800060fe  mov     [rsp+580h+var_548], r15d
0x180006103  test    rdi, rdi
0x180006106  jz      loc_1800063C7
0x18000610c  test    r14, r14
0x18000610f  jz      loc_1800063C7
0x180006115  xor     eax, eax
0x180006117  mov     [rsp+580h+var_560], r15
0x18000611c  mov     qword ptr [rsp+580h+var_530.dwMDDataTag], rax
0x180006121  lea     r8, [rsp+580h+var_544]
0x180006126  mov     rax, [rdi]
0x180006129  lea     rdx, aId; "id"
0x180006130  xorps   xmm0, xmm0
0x180006133  xor     r9d, r9d
0x180006136  mov     rcx, rdi
0x180006139  movups  xmmword ptr [rsp+580h+var_530.dwMDIdentifier], xmm0
0x18000613e  mov     rax, [rax+30h]
0x180006142  movups  xmmword ptr [rsp+580h+var_530.dwMDDataLen], xmm0
0x180006147  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000614c  mov     ebx, eax
0x18000614e  test    eax, eax
0x180006150  js      loc_1800063CC
0x180006156  mov     rax, [rdi]
0x180006159  lea     r8, [rsp+580h+var_550]
0x18000615e  xor     r9d, r9d
0x180006161  mov     [rsp+580h+var_560], r15
0x180006166  lea     rdx, aDatatype; "dataType"
0x18000616d  mov     rcx, rdi
0x180006170  mov     rax, [rax+30h]
0x180006174  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006179  mov     ebx, eax
0x18000617b  test    eax, eax
0x18000617d  js      loc_1800063CC
0x180006183  mov     rax, [rdi]
0x180006186  lea     r8, [rsp+580h+var_540]
0x18000618b  xor     r9d, r9d
0x18000618e  mov     [rsp+580h+var_560], r15
0x180006193  lea     rdx, aUsertype; "userType"
0x18000619a  mov     rcx, rdi
0x18000619d  mov     rax, [rax+30h]
0x1800061a1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800061a6  mov     ebx, eax
0x1800061a8  test    eax, eax
0x1800061aa  js      loc_1800063CC
0x1800061b0  mov     rax, [rdi]
0x1800061b3  lea     r8, [rsp+580h+var_53C]
0x1800061b8  xor     r9d, r9d
0x1800061bb  mov     [rsp+580h+var_560], r15
0x1800061c0  lea     rdx, aAttributes; "attributes"
0x1800061c7  mov     rcx, rdi
0x1800061ca  mov     rax, [rax+30h]
0x1800061ce  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800061d3  mov     ebx, eax
0x1800061d5  test    eax, eax
0x1800061d7  js      loc_1800063CC
0x1800061dd  mov     rax, [rdi]
0x1800061e0  lea     r8, [rsp+580h+String]
0x1800061e5  xor     r9d, r9d
0x1800061e8  mov     [rsp+580h+var_560], r15
0x1800061ed  lea     rdx, aValue; "value"
0x1800061f4  mov     rcx, rdi
0x1800061f7  mov     rax, [rax+40h]
0x1800061fb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006200  mov     ebx, eax
0x180006202  test    eax, eax
0x180006204  js      loc_1800063CC
0x18000620a  mov     ecx, [rsp+580h+var_550]
0x18000620e  cmp     ecx, 1
0x180006211  jnz     short loc_180006236
0x180006213  mov     rcx, [rsp+580h+String]; String
0x180006218  lea     r8d, [r15+0Ah]; Radix
0x18000621c  xor     edx, edx; EndPtr
0x18000621e  call    cs:__imp_wcstoul
0x180006224  mov     [rsp+580h+var_54C], eax
0x180006228  lea     rbx, [rsp+580h+var_54C]
0x18000622d  lea     edx, [r15+4]
0x180006231  jmp     loc_18000636E
0x180006236  lea     eax, [rcx-2]
0x180006239  test    eax, 0FFFFFFFDh
0x18000623e  jz      loc_180006374
0x180006244  cmp     ecx, 5
0x180006247  jnz     loc_180006315
0x18000624d  mov     rdi, [rsp+580h+String]
0x180006252  movzx   eax, word ptr [rdi]
0x180006255  test    ax, ax
0x180006258  jz      loc_1800062F8
0x18000625e  mov     rdx, r15
0x180006261  lea     esi, [rcx+5]
0x180006264  cmp     ax, 0Dh
0x180006268  jz      short loc_180006279
0x18000626a  cmp     ax, si
0x18000626d  jz      short loc_180006279
0x18000626f  test    rdx, rdx
0x180006272  jnz     short loc_1800062BA
0x180006274  mov     rdx, rdi
0x180006277  jmp     short loc_1800062BA
0x180006279  test    rdx, rdx
0x18000627c  jz      short loc_1800062BA
0x18000627e  mov     r8, rdi
0x180006281  lea     rcx, [rbp+480h+var_468]
0x180006285  sub     r8, rdx
0x180006288  sar     r8, 1
0x18000628b  call    cs:__imp_?Copy@STRU@@QEAAJPEBGK@Z; STRU::Copy(ushort const *,ulong)
0x180006291  mov     ebx, eax
0x180006293  test    eax, eax
0x180006295  js      loc_1800063CC
0x18000629b  lea     rcx, [rbp+480h+var_468]
0x18000629f  call    cs:__imp_?QueryStr@STRU@@QEAAPEAGXZ; STRU::QueryStr(void)
0x1800062a5  mov     rdx, rax
0x1800062a8  lea     rcx, [rsp+580h+var_508]
0x1800062ad  call    cs:__imp_?Append@MULTISZ@@QEAAHPEBG@Z; MULTISZ::Append(ushort const *)
0x1800062b3  test    eax, eax
0x1800062b5  jz      short loc_1800062DA
0x1800062b7  mov     rdx, r15
0x1800062ba  add     rdi, 2
0x1800062be  movzx   eax, word ptr [rdi]
0x1800062c1  test    ax, ax
0x1800062c4  jnz     short loc_180006264
0x1800062c6  test    rdx, rdx
0x1800062c9  jz      short loc_1800062F8
0x1800062cb  lea     rcx, [rsp+580h+var_508]
0x1800062d0  call    cs:__imp_?Append@MULTISZ@@QEAAHPEBG@Z; MULTISZ::Append(ushort const *)
0x1800062d6  test    eax, eax
0x1800062d8  jnz     short loc_1800062F8
0x1800062da  call    cs:__imp_GetLastError
0x1800062e0  mov     ebx, eax
0x1800062e2  test    eax, eax
0x1800062e4  jle     loc_1800063CC
0x1800062ea  movzx   ebx, ax
0x1800062ed  or      ebx, 80070000h
0x1800062f3  jmp     loc_1800063CC
0x1800062f8  lea     rcx, [rsp+580h+var_508]
0x1800062fd  call    cs:__imp_?QueryStr@MULTISZ@@QEBAPEAGXZ; MULTISZ::QueryStr(void)
0x180006303  lea     rcx, [rsp+580h+var_508]
0x180006308  mov     rbx, rax
0x18000630b  call    cs:__imp_?QueryCB@MULTISZ@@QEBAIXZ; MULTISZ::QueryCB(void)
0x180006311  mov     edx, eax
0x180006313  jmp     short loc_18000636E
0x180006315  cmp     ecx, 3
0x180006318  jnz     short loc_180006356
0x18000631a  mov     rdx, [rsp+580h+String]
0x18000631f  lea     rcx, [rbp+480h+var_4A0]
0x180006323  call    cs:__imp_?CopyW@STRA@@QEAAJPEBG@Z; STRA::CopyW(ushort const *)
0x180006329  mov     ebx, eax
0x18000632b  test    eax, eax
0x18000632d  js      loc_1800063CC
0x180006333  lea     rcx, [rbp+480h+var_4A0]
0x180006337  call    cs:__imp_?QueryStr@STRA@@QEAAPEADXZ; STRA::QueryStr(void)
0x18000633d  xor     r9d, r9d
0x180006340  lea     r8, [rsp+580h+var_548]
0x180006345  mov     rcx, rax
0x180006348  lea     rdx, [rbp+480h+var_4D0]
0x18000634c  call    cs:__imp_?uudecode@@YAHPEADPEAVBUFFER@@PEAKH@Z; uudecode(char *,BUFFER *,ulong *,int)
0x180006352  test    eax, eax
0x180006354  jnz     short loc_18000635D
0x180006356  mov     ebx, 8007000Dh
0x18000635b  jmp     short loc_1800063CC
0x18000635d  lea     rcx, [rbp+480h+var_4D0]
0x180006361  call    cs:__imp_?QueryPtr@BUFFER@@QEBAPEAXXZ; BUFFER::QueryPtr(void)
0x180006367  mov     edx, [rsp+580h+var_548]
0x18000636b  mov     rbx, rax
0x18000636e  mov     ecx, [rsp+580h+var_550]
0x180006372  jmp     short loc_18000638E
0x180006374  mov     rbx, [rsp+580h+String]
0x180006379  or      rax, 0FFFFFFFFFFFFFFFFh
0x18000637d  inc     rax
0x180006380  cmp     [rbx+rax*2], r15w
0x180006385  jnz     short loc_18000637D
0x180006387  lea     edx, ds:2[rax*2]
0x18000638e  mov     eax, [rsp+580h+var_544]
0x180006392  xor     r8d, r8d; int
0x180006395  mov     [rsp+580h+var_530.dwMDIdentifier], eax
0x180006399  mov     eax, [rsp+580h+var_540]
0x18000639d  mov     [rsp+580h+var_530.dwMDUserType], eax
0x1800063a1  mov     eax, [rsp+580h+var_53C]
0x1800063a5  mov     [rsp+580h+var_530.dwMDDataType], ecx
0x1800063a9  mov     rcx, r14; this
0x1800063ac  mov     [rsp+580h+var_530.dwMDDataLen], edx
0x1800063b0  lea     rdx, [rsp+580h+var_530]; struct _METADATA_RECORD *
0x1800063b5  mov     [rsp+580h+var_530.dwMDAttributes], eax
0x1800063b9  mov     [rsp+580h+var_530.pbMDData], rbx
0x1800063be  call    ?SetData@ABO_NODE@@QEAAJPEAU_METADATA_RECORD@@H@Z; ABO_NODE::SetData(_METADATA_RECORD *,int)
0x1800063c3  mov     ebx, eax
0x1800063c5  jmp     short loc_1800063CC
0x1800063c7  mov     ebx, 80070057h
0x1800063cc  lea     rcx, [rbp+480h+var_4D0]
0x1800063d0  call    cs:__imp_??1BUFFER@@QEAA@XZ; BUFFER::~BUFFER(void)
0x1800063d6  lea     rcx, [rbp+480h+var_4A0]
0x1800063da  call    cs:__imp_??1STRA@@QEAA@XZ; STRA::~STRA(void)
0x1800063e0  lea     rcx, [rbp+480h+var_468]
0x1800063e4  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x1800063ea  lea     rcx, [rsp+580h+var_508]
0x1800063ef  call    cs:__imp_??1MULTISZ@@QEAA@XZ; MULTISZ::~MULTISZ(void)
0x1800063f5  mov     eax, ebx
0x1800063f7  mov     rcx, [rbp+480h+var_30]
0x1800063fe  xor     rcx, rsp; StackCookie
0x180006401  call    __security_check_cookie
0x180006406  mov     rbx, [rsp+580h+arg_0]
0x18000640e  add     rsp, 560h
0x180006415  pop     r15
0x180006417  pop     r14
0x180006419  pop     rdi
0x18000641a  pop     rsi
0x18000641b  pop     rbp
0x18000641c  retn
```
