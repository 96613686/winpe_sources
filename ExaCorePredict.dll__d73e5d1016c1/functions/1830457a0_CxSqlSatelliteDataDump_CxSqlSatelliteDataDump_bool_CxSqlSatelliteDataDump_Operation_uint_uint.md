# CxSqlSatelliteDataDump::CxSqlSatelliteDataDump(bool,CxSqlSatelliteDataDump::Operation,uint,uint)

- ea: `0x1830457a0`
- end: `0x18304597d`
- name: `??0CxSqlSatelliteDataDump@@QEAA@_NW4Operation@0@II@Z`
- size: `477`
- prototype: ``
- caller_count: `2`
- callee_count: `10`
- tags: ``

## callers

- `0x183048c10`
- `0x18304eab0`

## callees

- `0x182d47420`
- `0x183045660`
- `0x1830456c0`
- `0x1830457a0`
- `0x18304feb0`
- `0x183053010`
- `0x183055940`
- `0x1830e8d10`
- `0x1832ce3b0`
- `0x1832dbeb0`

## import_xrefs

- `MSVCP140!?setstate@?$basic_ios@DU?$char_traits@D@std@@@std@@QEAAXH_N@Z` at `0x183045911`
- `MSVCP140!?setstate@?$basic_ios@DU?$char_traits@D@std@@@std@@QEAAXH_N@Z` at `0x183045911`
- `MSVCP140!?clear@?$basic_ios@DU?$char_traits@D@std@@@std@@QEAAXH_N@Z` at `0x18304591e`
- `MSVCP140!?clear@?$basic_ios@DU?$char_traits@D@std@@@std@@QEAAXH_N@Z` at `0x18304591e`
- `MSVCP140!?bad@ios_base@std@@QEBA_NXZ` at `0x183045938`
- `MSVCP140!?bad@ios_base@std@@QEBA_NXZ` at `0x183045938`

## string_xrefs

- `0x183045839`: `write`
- `0x183045830`: `readparam`
- `0x183045827`: `writeparam`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CxSqlSatelliteDataDump::CxSqlSatelliteDataDump(__int64 a1, char a2, int a3, int a4, int a5)
{
  int v9; // esi
  int v10; // esi
  const char *v11; // r8
  const char *DefaultDataDir; // rax
  const char *CharPointer; // rax
  __int64 v14; // rax
  __int64 v15; // rcx
  int v17; // [rsp+20h] [rbp-108h]
  _QWORD v18[2]; // [rsp+80h] [rbp-A8h] BYREF
  char Buffer[112]; // [rsp+90h] [rbp-98h] BYREF

  std::ofstream::ofstream(a1, 1);
  *(_BYTE *)(a1 + 264) = a2;
  if ( a2 )
  {
    memset_0(Buffer, 0, 0x64u);
    if ( a3 )
    {
      v9 = a3 - 1;
      if ( v9 )
      {
        v10 = v9 - 1;
        if ( v10 )
        {
          if ( v10 == 1 )
            v11 = "writeparam";
          else
            v11 = "null";
        }
        else
        {
          v11 = "readparam";
        }
      }
      else
      {
        v11 = "write";
      }
    }
    else
    {
      v11 = "read";
    }
    if ( sprintf_s<100>(Buffer, "%s-%04d-%02d.txt", v11, a4, a5) == -1 )
    {
      *(_BYTE *)(a1 + 264) = 0;
    }
    else
    {
      v18[0] = 0;
      DefaultDataDir = GetDefaultDataDir();
      LOBYTE(v17) = 0;
      CheckAndFixDataFileName(v18, Buffer, ".txt", DefaultDataDir, v17, 0, 0, 1, 0, 0, 0, 1, 0);
      CharPointer = CxString::GetCharPointer((CxString *)v18);
      v14 = std::filebuf::open(a1 + 8, CharPointer, 42, 64);
      v15 = *(int *)(*(_QWORD *)a1 + 4LL);
      if ( v14 )
        std::ios::clear(a1 + v15, 0, 0);
      else
        std::ios::setstate(a1 + v15, 2);
      if ( !*(_QWORD *)(a1 + 136) || std::ios_base::bad((std::ios_base *)(a1 + *(int *)(*(_QWORD *)a1 + 4LL))) )
        *(_BYTE *)(a1 + 264) = 0;
      CxString::~CxString((CxString *)v18);
    }
  }
  return a1;
}

```

## disassembly

```asm
0x1830457a0  push    rbp
0x1830457a2  push    rsi
0x1830457a3  push    rdi
0x1830457a4  sub     rsp, 110h
0x1830457ab  mov     [rsp+128h+var_B8], 0FFFFFFFFFFFFFFFEh
0x1830457b4  mov     [rsp+128h+arg_8], rbx
0x1830457bc  mov     rax, cs:__security_cookie
0x1830457c3  xor     rax, rsp
0x1830457c6  mov     [rsp+128h+var_28], rax
0x1830457ce  mov     ebp, r9d
0x1830457d1  mov     esi, r8d
0x1830457d4  movzx   ebx, dl
0x1830457d7  mov     rdi, rcx
0x1830457da  mov     [rsp+128h+var_B0], rcx
0x1830457df  mov     edx, 1
0x1830457e4  call    ??0?$basic_ofstream@DU?$char_traits@D@std@@@std@@QEAA@XZ; std::ofstream::ofstream(void)
0x1830457e9  nop
0x1830457ea  mov     [rdi+108h], bl
0x1830457f0  test    bl, bl
0x1830457f2  jz      loc_183045957
0x1830457f8  xor     edx, edx; Val
0x1830457fa  lea     r8d, [rdx+64h]; Size
0x1830457fe  lea     rcx, [rsp+128h+Buffer]; void *
0x183045806  call    memset_0
0x18304580b  test    esi, esi
0x18304580d  jz      short loc_183045842
0x18304580f  sub     esi, 1
0x183045812  jz      short loc_183045839
0x183045814  sub     esi, 1
0x183045817  jz      short loc_183045830
0x183045819  cmp     esi, 1
0x18304581c  jz      short loc_183045827
0x18304581e  lea     r8, aNull; "null"
0x183045825  jmp     short loc_183045849
0x183045827  lea     r8, aWriteparam; "writeparam"
0x18304582e  jmp     short loc_183045849
0x183045830  lea     r8, aReadparam; "readparam"
0x183045837  jmp     short loc_183045849
0x183045839  lea     r8, aWrite; "write"
0x183045840  jmp     short loc_183045849
0x183045842  lea     r8, aRead; "read"
0x183045849  mov     ecx, [rsp+128h+arg_20]
0x183045850  mov     [rsp+128h+var_108], ecx
0x183045854  mov     r9d, ebp
0x183045857  lea     rdx, aS04d02dTxt; "%s-%04d-%02d.txt"
0x18304585e  lea     rcx, [rsp+128h+Buffer]; Buffer
0x183045866  call    ??$sprintf_s@$0GE@@@YAHAEAY0GE@DPEBDZZ; sprintf_s<100>(char (&)[100],char const *,...)
0x18304586b  cmp     eax, 0FFFFFFFFh
0x18304586e  jnz     short loc_18304587C
0x183045870  mov     byte ptr [rdi+108h], 0
0x183045877  jmp     loc_183045957
0x18304587c  xor     eax, eax
0x18304587e  mov     [rsp+128h+var_A8], rax
0x183045886  call    ?GetDefaultDataDir@@YAPEBDXZ; GetDefaultDataDir(void)
0x18304588b  mov     r9, rax
0x18304588e  mov     [rsp+128h+var_C8], 0
0x183045893  mov     [rsp+128h+var_D0], 1
0x183045898  mov     [rsp+128h+var_D8], 0
0x18304589d  mov     [rsp+128h+var_E0], 0
0x1830458a2  mov     [rsp+128h+var_E8], 0
0x1830458a7  mov     [rsp+128h+var_F0], 1
0x1830458ac  mov     [rsp+128h+var_F8], 0
0x1830458b1  mov     [rsp+128h+var_100], 0
0x1830458b6  mov     byte ptr [rsp+128h+var_108], 0
0x1830458bb  lea     r8, aTxt; ".txt"
0x1830458c2  lea     rdx, [rsp+128h+Buffer]
0x1830458ca  lea     rcx, [rsp+128h+var_A8]
0x1830458d2  call    ?CheckAndFixDataFileName@@YA?AVCxString@@PEBD_N11111@Z; CheckAndFixDataFileName(char const *,bool,bool,bool,bool,bool,bool)
0x1830458d7  nop
0x1830458d8  lea     rcx, [rsp+128h+var_A8]; this
0x1830458e0  call    ?GetCharPointer@CxString@@QEBAPEBDXZ; CxString::GetCharPointer(void)
0x1830458e5  lea     rcx, [rdi+8]
0x1830458e9  mov     r9d, 40h ; '@'
0x1830458ef  lea     r8d, [r9-16h]
0x1830458f3  mov     rdx, rax
0x1830458f6  call    ?open@?$basic_filebuf@DU?$char_traits@D@std@@@std@@QEAAPEAV12@PEBDHH@Z; std::filebuf::open(char const *,int,int)
0x1830458fb  xor     r8d, r8d
0x1830458fe  test    rax, rax
0x183045901  mov     rax, [rdi]
0x183045904  movsxd  rcx, dword ptr [rax+4]
0x183045908  jnz     short loc_183045919
0x18304590a  add     rcx, rdi
0x18304590d  lea     edx, [r8+2]
0x183045911  call    cs:__imp_?setstate@?$basic_ios@DU?$char_traits@D@std@@@std@@QEAAXH_N@Z; std::ios::setstate(int,bool)
0x183045917  jmp     short loc_183045924
0x183045919  add     rcx, rdi
0x18304591c  xor     edx, edx
0x18304591e  call    cs:__imp_?clear@?$basic_ios@DU?$char_traits@D@std@@@std@@QEAAXH_N@Z; std::ios::clear(int,bool)
0x183045924  cmp     qword ptr [rdi+88h], 0
0x18304592c  jz      short loc_183045942
0x18304592e  mov     rax, [rdi]
0x183045931  movsxd  rcx, dword ptr [rax+4]
0x183045935  add     rcx, rdi
0x183045938  call    cs:__imp_?bad@ios_base@std@@QEBA_NXZ; std::ios_base::bad(void)
0x18304593e  test    al, al
0x183045940  jz      short loc_183045949
0x183045942  mov     byte ptr [rdi+108h], 0
0x183045949  lea     rcx, [rsp+128h+var_A8]; this
0x183045951  call    ??1CxString@@QEAA@XZ; CxString::~CxString(void)
0x183045956  nop
0x183045957  mov     rax, rdi
0x18304595a  mov     rcx, [rsp+128h+var_28]
0x183045962  xor     rcx, rsp; StackCookie
0x183045965  call    __security_check_cookie
0x18304596a  mov     rbx, [rsp+128h+arg_8]
0x183045972  add     rsp, 110h
0x183045979  pop     rdi
0x18304597a  pop     rsi
0x18304597b  pop     rbp
0x18304597c  retn
```
