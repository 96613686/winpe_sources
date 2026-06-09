# StateRepository::Entity::ApplicationExtension::BindAndExecuteForAddOrUpdate(StateRepository::Database &,char const *,bool,StateRepository::ExecutionFlags)

- ea: `0x18001e0c8`
- end: `0x18001e515`
- name: `?BindAndExecuteForAddOrUpdate@ApplicationExtension@Entity@StateRepository@@AEAAJAEAVDatabase@3@PEBD_NW4ExecutionFlags@3@@Z`
- size: `1101`
- prototype: `int __high(struct StateRepository::Database *, const char *, bool, enum StateRepository::ExecutionFlags)`
- caller_count: `1`
- callee_count: `14`
- tags: `loader_planting, installer_update`

## callers

- `0x18001e89c`

## callees

- `0x18000a3c0`
- `0x18000c3bc`
- `0x1800182f8`
- `0x180018e04`
- `0x180019614`
- `0x18001b5a8`
- `0x18001b5dc`
- `0x18001b64c`
- `0x18001b6bc`
- `0x18001b750`
- `0x18001b810`
- `0x18001b8d4`
- `0x18001e0c8`
- `0x180029f90`

## string_xrefs

- `0x18001e136`: `onecore\base\appmodel\staterepository\dataaccesslayer\entity-applicationextension.cpp`
- `0x18001e451`: `onecore\base\appmodel\staterepository\dataaccesslayer\entity-applicationextension.cpp`
- `0x18001e49e`: `onecore\base\appmodel\staterepository\dataaccesslayer\entity-applicationextension.cpp`
- `0x18001e485`: `SELECT EXISTS(SELECT 1 FROM ApplicationExtension WHERE _ApplicationExtensionID=? AND _WorkId=0 LIMIT 1);`
- `0x18001e479`: `SELECT EXISTS(SELECT 1 FROM ApplicationExtension WHERE _ApplicationExtensionID=? AND (_WorkId=0 OR _WorkId=?) LIMIT 1);`

## pseudocode

```c
__int64 __fastcall StateRepository::Entity::ApplicationExtension::BindAndExecuteForAddOrUpdate(
        __int64 a1,
        StateRepository::Database *a2,
        const char *a3,
        char a4)
{
  int NoRow; // eax
  unsigned int v7; // ebx
  __int64 v8; // rdx
  __int64 v9; // r9
  wil::details::in1diag3 *v10; // rcx
  __int64 v11; // r14
  int v12; // eax
  const char *v13; // r9
  int v14; // eax
  int v16; // [rsp+20h] [rbp-20h]
  bool *v17; // [rsp+28h] [rbp-18h]
  _QWORD v18[2]; // [rsp+30h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+18h]
  __int64 v20; // [rsp+78h] [rbp+38h] BYREF

  LOBYTE(v20) = a4;
  v18[0] = 0;
  NoRow = StateRepository::Database::PrepareFromCache(a2, a3, (struct StateRepository::Statement *)v18);
  v7 = NoRow;
  if ( NoRow < 0 )
  {
    v8 = 1152;
LABEL_5:
    v9 = (unsigned int)NoRow;
    goto LABEL_6;
  }
  NoRow = StateRepository::Statement::Bind((StateRepository::Statement *)v18, 1, *(_QWORD *)(a1 + 8) + 1LL);
  v7 = NoRow;
  if ( NoRow < 0 )
  {
    v8 = 1153;
    goto LABEL_5;
  }
  v11 = *((_QWORD *)a2 + 1);
  NoRow = StateRepository::Statement::Bind((StateRepository::Statement *)v18, 2, v11);
  v7 = NoRow;
  if ( NoRow < 0 )
  {
    v8 = 1155;
    goto LABEL_5;
  }
  NoRow = StateRepository::Statement::Bind((StateRepository::Statement *)v18, 3, *(_QWORD *)(a1 + 24));
  v7 = NoRow;
  if ( NoRow < 0 )
  {
    v8 = 1156;
    goto LABEL_5;
  }
  NoRow = StateRepository::Statement::Bind((StateRepository::Statement *)v18, 4, *(_DWORD *)(a1 + 32));
  v7 = NoRow;
  if ( NoRow < 0 )
  {
    v8 = 1157;
    goto LABEL_5;
  }
  NoRow = StateRepository::Statement::BindAddress(
            (StateRepository::Statement *)v18,
            5,
            *(const unsigned __int16 **)(a1 + 40));
  v7 = NoRow;
  if ( NoRow < 0 )
  {
    v8 = 1158;
    goto LABEL_5;
  }
  NoRow = StateRepository::Statement::Bind((StateRepository::Statement *)v18, 6, *(_QWORD *)(a1 + 56));
  v7 = NoRow;
  if ( NoRow < 0 )
  {
    v8 = 1159;
    goto LABEL_5;
  }
  NoRow = StateRepository::Statement::BindAddress(
            (StateRepository::Statement *)v18,
            7,
            *(const unsigned __int16 **)(a1 + 64));
  v7 = NoRow;
  if ( NoRow < 0 )
  {
    v8 = 1160;
    goto LABEL_5;
  }
  NoRow = StateRepository::Statement::BindAddress(
            (StateRepository::Statement *)v18,
            8,
            *(const unsigned __int16 **)(a1 + 80));
  v7 = NoRow;
  if ( NoRow < 0 )
  {
    v8 = 1161;
    goto LABEL_5;
  }
  NoRow = StateRepository::Statement::BindAddress(
            (StateRepository::Statement *)v18,
            9,
            *(const unsigned __int16 **)(a1 + 96));
  v7 = NoRow;
  if ( NoRow < 0 )
  {
    v8 = 1162;
    goto LABEL_5;
  }
  NoRow = StateRepository::Statement::BindAddress(
            (StateRepository::Statement *)v18,
            10,
            *(const unsigned __int16 **)(a1 + 112));
  v7 = NoRow;
  if ( NoRow < 0 )
  {
    v8 = 1163;
    goto LABEL_5;
  }
  NoRow = StateRepository::Statement::BindAddress(
            (StateRepository::Statement *)v18,
            11,
            *(const unsigned __int16 **)(a1 + 128));
  v7 = NoRow;
  if ( NoRow < 0 )
  {
    v8 = 1164;
    goto LABEL_5;
  }
  NoRow = StateRepository::Statement::BindAddress(
            (StateRepository::Statement *)v18,
            12,
            *(const unsigned __int16 **)(a1 + 144));
  v7 = NoRow;
  if ( NoRow < 0 )
  {
    v8 = 1165;
    goto LABEL_5;
  }
  NoRow = StateRepository::Statement::Bind((StateRepository::Statement *)v18, 13, *(_DWORD *)(a1 + 160));
  v7 = NoRow;
  if ( NoRow < 0 )
  {
    v8 = 1166;
    goto LABEL_5;
  }
  NoRow = StateRepository::Statement::Bind((StateRepository::Statement *)v18, 14, *(_DWORD *)(a1 + 164));
  v7 = NoRow;
  if ( NoRow < 0 )
  {
    v8 = 1167;
    goto LABEL_5;
  }
  NoRow = StateRepository::Statement::BindAddress(
            (StateRepository::Statement *)v18,
            15,
            *(const unsigned __int16 **)(a1 + 168));
  v7 = NoRow;
  if ( NoRow < 0 )
  {
    v8 = 1168;
    goto LABEL_5;
  }
  NoRow = StateRepository::Statement::BindAddress(
            (StateRepository::Statement *)v18,
            16,
            *(const unsigned __int16 **)(a1 + 184));
  v7 = NoRow;
  if ( NoRow < 0 )
  {
    v8 = 1169;
    goto LABEL_5;
  }
  NoRow = StateRepository::Statement::BindAddress(
            (StateRepository::Statement *)v18,
            17,
            *(const unsigned __int16 **)(a1 + 200));
  v7 = NoRow;
  if ( NoRow < 0 )
  {
    v8 = 1170;
    goto LABEL_5;
  }
  NoRow = StateRepository::Statement::BindAddress(
            (StateRepository::Statement *)v18,
            18,
            (const struct StateRepository::Blob *)(a1 + 216));
  v7 = NoRow;
  if ( NoRow < 0 )
  {
    v8 = 1171;
    goto LABEL_5;
  }
  NoRow = StateRepository::Statement::BindAddress(
            (StateRepository::Statement *)v18,
            19,
            (const struct StateRepository::Blob *)(a1 + 240));
  v7 = NoRow;
  if ( NoRow < 0 )
  {
    v8 = 1172;
    goto LABEL_5;
  }
  NoRow = StateRepository::Statement::Bind((StateRepository::Statement *)v18, 20, *(_QWORD *)a1);
  v7 = NoRow;
  if ( NoRow < 0 )
  {
    v8 = 1175;
    goto LABEL_5;
  }
  NoRow = StateRepository::Statement::Bind((StateRepository::Statement *)v18, 21, *(_QWORD *)(a1 + 8));
  v7 = NoRow;
  if ( NoRow < 0 )
  {
    v8 = 1176;
    goto LABEL_5;
  }
  NoRow = StateRepository::Statement::BindIfWorkInProgress((StateRepository::Statement *)v18, 22, v11);
  v7 = NoRow;
  if ( NoRow < 0 )
  {
    v8 = 1177;
    goto LABEL_5;
  }
  NoRow = StateRepository::Statement::FetchNoRow((StateRepository::Statement *)v18);
  v7 = NoRow;
  if ( NoRow < 0 )
  {
    v8 = 1180;
    goto LABEL_5;
  }
  v12 = StateRepository::Database::AddToCache(a2, (struct StateRepository::Statement *)v18);
  if ( v12 < 0 )
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x49E,
      (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\entity-applicationextension.cpp",
      (const char *)(unsigned int)v12,
      v16);
  if ( (unsigned int)StateRepository::Database::GetChanges(a2) == 1 )
  {
    ++*(_QWORD *)(a1 + 8);
    v7 = 0;
    *(_QWORD *)(a1 + 16) = v11;
    goto LABEL_61;
  }
  v13 = *(const char **)a1;
  LOBYTE(v20) = 0;
  v14 = StateRepository::StatementExecution::PrepareAndBindAndExists(
          a2,
          (struct StateRepository::Database *)"SELECT EXISTS(SELECT 1 FROM ApplicationExtension WHERE _ApplicationExtensi"
                                              "onID=? AND _WorkId=0 LIMIT 1);",
          "SELECT EXISTS(SELECT 1 FROM ApplicationExtension WHERE _ApplicationExtensionID=? AND (_WorkId=0 OR _WorkId=?) LIMIT 1);",
          v13,
          (__int64)&v20,
          v17);
  v10 = retaddr;
  v7 = v14;
  if ( v14 >= 0 )
  {
    if ( (_BYTE)v20 )
    {
      v7 = -2140733439;
      v8 = 1197;
      v9 = 2154233857LL;
    }
    else
    {
      v7 = -2147023728;
      v8 = 1198;
      v9 = 2147943568LL;
    }
    goto LABEL_7;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x23A,
    (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\entity-applicationextension.cpp",
    (const char *)(unsigned int)v14,
    v16);
  v9 = v7;
  v8 = 1196;
LABEL_6:
  v10 = retaddr;
LABEL_7:
  wil::details::in1diag3::Return_Hr(
    v10,
    (void *)v8,
    (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\entity-applicationextension.cpp",
    (const char *)v9,
    v16);
LABEL_61:
  StateRepository::Statement::~Statement((StateRepository::Statement *)v18);
  return v7;
}

```

## disassembly

```asm
0x18001e0c8  mov     [rsp-18h+arg_0], rbx
0x18001e0cd  mov     [rsp-18h+arg_8], rsi
0x18001e0d2  mov     byte ptr [rsp-18h+arg_18], r9b
0x18001e0d7  push    rbp
0x18001e0d8  push    rdi
0x18001e0d9  push    r14
0x18001e0db  mov     rbp, rsp
0x18001e0de  sub     rsp, 40h
0x18001e0e2  mov     rax, r8
0x18001e0e5  mov     [rbp+var_10], 0
0x18001e0ed  mov     rsi, rdx
0x18001e0f0  lea     r8, [rbp+var_10]; struct StateRepository::Statement *
0x18001e0f4  mov     rdi, rcx
0x18001e0f7  mov     rdx, rax; char *
0x18001e0fa  mov     rcx, rsi; this
0x18001e0fd  call    ?PrepareFromCache@Database@StateRepository@@QEAAJPEBDAEAVStatement@2@@Z; StateRepository::Database::PrepareFromCache(char const *,StateRepository::Statement &)
0x18001e102  mov     ebx, eax
0x18001e104  test    eax, eax
0x18001e106  jns     short loc_18001E10F
0x18001e108  mov     edx, 480h
0x18001e10d  jmp     short loc_18001E12F
0x18001e10f  mov     r8, [rdi+8]
0x18001e113  lea     rcx, [rbp+var_10]; this
0x18001e117  inc     r8; __int64
0x18001e11a  mov     edx, 1; int
0x18001e11f  call    ?Bind@Statement@StateRepository@@QEAAJH_J@Z; StateRepository::Statement::Bind(int,__int64)
0x18001e124  mov     ebx, eax
0x18001e126  test    eax, eax
0x18001e128  jns     short loc_18001E147
0x18001e12a  mov     edx, 481h; void *
0x18001e12f  mov     r9d, eax; char *
0x18001e132  mov     rcx, [rbp+18h]; this
0x18001e136  lea     r8, aOnecoreBaseApp_30; "onecore\\base\\appmodel\\staterepositor"...
0x18001e13d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001e142  jmp     loc_18001E4F7
0x18001e147  mov     r14, [rsi+8]
0x18001e14b  lea     rcx, [rbp+var_10]; this
0x18001e14f  mov     r8, r14; __int64
0x18001e152  mov     edx, 2; int
0x18001e157  call    ?Bind@Statement@StateRepository@@QEAAJH_J@Z; StateRepository::Statement::Bind(int,__int64)
0x18001e15c  mov     ebx, eax
0x18001e15e  test    eax, eax
0x18001e160  jns     short loc_18001E169
0x18001e162  mov     edx, 483h
0x18001e167  jmp     short loc_18001E12F
0x18001e169  mov     r8, [rdi+18h]; __int64
0x18001e16d  lea     rcx, [rbp+var_10]; this
0x18001e171  mov     edx, 3; int
0x18001e176  call    ?Bind@Statement@StateRepository@@QEAAJH_J@Z; StateRepository::Statement::Bind(int,__int64)
0x18001e17b  mov     ebx, eax
0x18001e17d  test    eax, eax
0x18001e17f  jns     short loc_18001E188
0x18001e181  mov     edx, 484h
0x18001e186  jmp     short loc_18001E12F
0x18001e188  mov     r8d, [rdi+20h]; int
0x18001e18c  lea     rcx, [rbp+var_10]; this
0x18001e190  mov     edx, 4; int
0x18001e195  call    ?Bind@Statement@StateRepository@@QEAAJHH@Z; StateRepository::Statement::Bind(int,int)
0x18001e19a  mov     ebx, eax
0x18001e19c  test    eax, eax
0x18001e19e  jns     short loc_18001E1A7
0x18001e1a0  mov     edx, 485h
0x18001e1a5  jmp     short loc_18001E12F
0x18001e1a7  mov     r8, [rdi+28h]; unsigned __int16 *
0x18001e1ab  lea     rcx, [rbp+var_10]; this
0x18001e1af  mov     edx, 5; int
0x18001e1b4  call    ?BindAddress@Statement@StateRepository@@QEAAJHPEBG@Z; StateRepository::Statement::BindAddress(int,ushort const *)
0x18001e1b9  mov     ebx, eax
0x18001e1bb  test    eax, eax
0x18001e1bd  jns     short loc_18001E1C9
0x18001e1bf  mov     edx, 486h
0x18001e1c4  jmp     loc_18001E12F
0x18001e1c9  mov     r8, [rdi+38h]; __int64
0x18001e1cd  lea     rcx, [rbp+var_10]; this
0x18001e1d1  mov     edx, 6; int
0x18001e1d6  call    ?Bind@Statement@StateRepository@@QEAAJH_J@Z; StateRepository::Statement::Bind(int,__int64)
0x18001e1db  mov     ebx, eax
0x18001e1dd  test    eax, eax
0x18001e1df  jns     short loc_18001E1EB
0x18001e1e1  mov     edx, 487h
0x18001e1e6  jmp     loc_18001E12F
0x18001e1eb  mov     r8, [rdi+40h]; unsigned __int16 *
0x18001e1ef  lea     rcx, [rbp+var_10]; this
0x18001e1f3  mov     edx, 7; int
0x18001e1f8  call    ?BindAddress@Statement@StateRepository@@QEAAJHPEBG@Z; StateRepository::Statement::BindAddress(int,ushort const *)
0x18001e1fd  mov     ebx, eax
0x18001e1ff  test    eax, eax
0x18001e201  jns     short loc_18001E20D
0x18001e203  mov     edx, 488h
0x18001e208  jmp     loc_18001E12F
0x18001e20d  mov     r8, [rdi+50h]; unsigned __int16 *
0x18001e211  lea     rcx, [rbp+var_10]; this
0x18001e215  mov     edx, 8; int
0x18001e21a  call    ?BindAddress@Statement@StateRepository@@QEAAJHPEBG@Z; StateRepository::Statement::BindAddress(int,ushort const *)
0x18001e21f  mov     ebx, eax
0x18001e221  test    eax, eax
0x18001e223  jns     short loc_18001E22F
0x18001e225  mov     edx, 489h
0x18001e22a  jmp     loc_18001E12F
0x18001e22f  mov     r8, [rdi+60h]; unsigned __int16 *
0x18001e233  lea     rcx, [rbp+var_10]; this
0x18001e237  mov     edx, 9; int
0x18001e23c  call    ?BindAddress@Statement@StateRepository@@QEAAJHPEBG@Z; StateRepository::Statement::BindAddress(int,ushort const *)
0x18001e241  mov     ebx, eax
0x18001e243  test    eax, eax
0x18001e245  jns     short loc_18001E251
0x18001e247  mov     edx, 48Ah
0x18001e24c  jmp     loc_18001E12F
0x18001e251  mov     r8, [rdi+70h]; unsigned __int16 *
0x18001e255  lea     rcx, [rbp+var_10]; this
0x18001e259  mov     edx, 0Ah; int
0x18001e25e  call    ?BindAddress@Statement@StateRepository@@QEAAJHPEBG@Z; StateRepository::Statement::BindAddress(int,ushort const *)
0x18001e263  mov     ebx, eax
0x18001e265  test    eax, eax
0x18001e267  jns     short loc_18001E273
0x18001e269  mov     edx, 48Bh
0x18001e26e  jmp     loc_18001E12F
0x18001e273  mov     r8, [rdi+80h]; unsigned __int16 *
0x18001e27a  lea     rcx, [rbp+var_10]; this
0x18001e27e  mov     edx, 0Bh; int
0x18001e283  call    ?BindAddress@Statement@StateRepository@@QEAAJHPEBG@Z; StateRepository::Statement::BindAddress(int,ushort const *)
0x18001e288  mov     ebx, eax
0x18001e28a  test    eax, eax
0x18001e28c  jns     short loc_18001E298
0x18001e28e  mov     edx, 48Ch
0x18001e293  jmp     loc_18001E12F
0x18001e298  mov     r8, [rdi+90h]; unsigned __int16 *
0x18001e29f  lea     rcx, [rbp+var_10]; this
0x18001e2a3  mov     edx, 0Ch; int
0x18001e2a8  call    ?BindAddress@Statement@StateRepository@@QEAAJHPEBG@Z; StateRepository::Statement::BindAddress(int,ushort const *)
0x18001e2ad  mov     ebx, eax
0x18001e2af  test    eax, eax
0x18001e2b1  jns     short loc_18001E2BD
0x18001e2b3  mov     edx, 48Dh
0x18001e2b8  jmp     loc_18001E12F
0x18001e2bd  mov     r8d, [rdi+0A0h]; int
0x18001e2c4  lea     rcx, [rbp+var_10]; this
0x18001e2c8  mov     edx, 0Dh; int
0x18001e2cd  call    ?Bind@Statement@StateRepository@@QEAAJHH@Z; StateRepository::Statement::Bind(int,int)
0x18001e2d2  mov     ebx, eax
0x18001e2d4  test    eax, eax
0x18001e2d6  jns     short loc_18001E2E2
0x18001e2d8  mov     edx, 48Eh
0x18001e2dd  jmp     loc_18001E12F
0x18001e2e2  mov     r8d, [rdi+0A4h]; int
0x18001e2e9  lea     rcx, [rbp+var_10]; this
0x18001e2ed  mov     edx, 0Eh; int
0x18001e2f2  call    ?Bind@Statement@StateRepository@@QEAAJHH@Z; StateRepository::Statement::Bind(int,int)
0x18001e2f7  mov     ebx, eax
0x18001e2f9  test    eax, eax
0x18001e2fb  jns     short loc_18001E307
0x18001e2fd  mov     edx, 48Fh
0x18001e302  jmp     loc_18001E12F
0x18001e307  mov     r8, [rdi+0A8h]; unsigned __int16 *
0x18001e30e  lea     rcx, [rbp+var_10]; this
0x18001e312  mov     edx, 0Fh; int
0x18001e317  call    ?BindAddress@Statement@StateRepository@@QEAAJHPEBG@Z; StateRepository::Statement::BindAddress(int,ushort const *)
0x18001e31c  mov     ebx, eax
0x18001e31e  test    eax, eax
0x18001e320  jns     short loc_18001E32C
0x18001e322  mov     edx, 490h
0x18001e327  jmp     loc_18001E12F
0x18001e32c  mov     r8, [rdi+0B8h]; unsigned __int16 *
0x18001e333  lea     rcx, [rbp+var_10]; this
0x18001e337  mov     edx, 10h; int
0x18001e33c  call    ?BindAddress@Statement@StateRepository@@QEAAJHPEBG@Z; StateRepository::Statement::BindAddress(int,ushort const *)
0x18001e341  mov     ebx, eax
0x18001e343  test    eax, eax
0x18001e345  jns     short loc_18001E351
0x18001e347  mov     edx, 491h
0x18001e34c  jmp     loc_18001E12F
0x18001e351  mov     r8, [rdi+0C8h]; unsigned __int16 *
0x18001e358  lea     rcx, [rbp+var_10]; this
0x18001e35c  mov     edx, 11h; int
0x18001e361  call    ?BindAddress@Statement@StateRepository@@QEAAJHPEBG@Z; StateRepository::Statement::BindAddress(int,ushort const *)
0x18001e366  mov     ebx, eax
0x18001e368  test    eax, eax
0x18001e36a  jns     short loc_18001E376
0x18001e36c  mov     edx, 492h
0x18001e371  jmp     loc_18001E12F
0x18001e376  lea     r8, [rdi+0D8h]; struct StateRepository::Blob *
0x18001e37d  mov     edx, 12h; int
0x18001e382  lea     rcx, [rbp+var_10]; this
0x18001e386  call    ?BindAddress@Statement@StateRepository@@QEAAJHAEBVBlob@2@@Z; StateRepository::Statement::BindAddress(int,StateRepository::Blob const &)
0x18001e38b  mov     ebx, eax
0x18001e38d  test    eax, eax
0x18001e38f  jns     short loc_18001E39B
0x18001e391  mov     edx, 493h
0x18001e396  jmp     loc_18001E12F
0x18001e39b  lea     r8, [rdi+0F0h]; struct StateRepository::Blob *
0x18001e3a2  mov     edx, 13h; int
0x18001e3a7  lea     rcx, [rbp+var_10]; this
0x18001e3ab  call    ?BindAddress@Statement@StateRepository@@QEAAJHAEBVBlob@2@@Z; StateRepository::Statement::BindAddress(int,StateRepository::Blob const &)
0x18001e3b0  mov     ebx, eax
0x18001e3b2  test    eax, eax
0x18001e3b4  jns     short loc_18001E3C0
0x18001e3b6  mov     edx, 494h
0x18001e3bb  jmp     loc_18001E12F
0x18001e3c0  mov     r8, [rdi]; __int64
0x18001e3c3  lea     rcx, [rbp+var_10]; this
0x18001e3c7  mov     edx, 14h; int
0x18001e3cc  call    ?Bind@Statement@StateRepository@@QEAAJH_J@Z; StateRepository::Statement::Bind(int,__int64)
0x18001e3d1  mov     ebx, eax
0x18001e3d3  test    eax, eax
0x18001e3d5  jns     short loc_18001E3E1
0x18001e3d7  mov     edx, 497h
0x18001e3dc  jmp     loc_18001E12F
0x18001e3e1  mov     r8, [rdi+8]; __int64
0x18001e3e5  lea     rcx, [rbp+var_10]; this
0x18001e3e9  mov     edx, 15h; int
0x18001e3ee  call    ?Bind@Statement@StateRepository@@QEAAJH_J@Z; StateRepository::Statement::Bind(int,__int64)
0x18001e3f3  mov     ebx, eax
0x18001e3f5  test    eax, eax
0x18001e3f7  jns     short loc_18001E403
0x18001e3f9  mov     edx, 498h
0x18001e3fe  jmp     loc_18001E12F
0x18001e403  mov     r8, r14; __int64
0x18001e406  lea     rcx, [rbp+var_10]; this
0x18001e40a  mov     edx, 16h; int
0x18001e40f  call    ?BindIfWorkInProgress@Statement@StateRepository@@QEAAJH_J@Z; StateRepository::Statement::BindIfWorkInProgress(int,__int64)
0x18001e414  mov     ebx, eax
0x18001e416  test    eax, eax
0x18001e418  jns     short loc_18001E424
0x18001e41a  mov     edx, 499h
0x18001e41f  jmp     loc_18001E12F
0x18001e424  lea     rcx, [rbp+var_10]; this
0x18001e428  call    ?FetchNoRow@Statement@StateRepository@@QEAAJXZ; StateRepository::Statement::FetchNoRow(void)
0x18001e42d  mov     ebx, eax
0x18001e42f  test    eax, eax
0x18001e431  jns     short loc_18001E43D
0x18001e433  mov     edx, 49Ch
0x18001e438  jmp     loc_18001E12F
0x18001e43d  lea     rdx, [rbp+var_10]; struct StateRepository::Statement *
0x18001e441  mov     rcx, rsi; this
0x18001e444  call    ?AddToCache@Database@StateRepository@@QEAAJAEAVStatement@2@@Z; StateRepository::Database::AddToCache(StateRepository::Statement &)
0x18001e449  test    eax, eax
0x18001e44b  jns     short loc_18001E465
0x18001e44d  mov     rcx, [rbp+18h]; this
0x18001e451  lea     r8, aOnecoreBaseApp_30; "onecore\\base\\appmodel\\staterepositor"...
0x18001e458  mov     r9d, eax; char *
0x18001e45b  mov     edx, 49Eh; void *
0x18001e460  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18001e465  mov     rcx, rsi; this
0x18001e468  call    ?GetChanges@Database@StateRepository@@QEBAHXZ; StateRepository::Database::GetChanges(void)
0x18001e46d  cmp     eax, 1
0x18001e470  jz      short loc_18001E4ED
0x18001e472  mov     r9, [rdi]; char *
0x18001e475  lea     rax, [rbp+arg_18]
0x18001e479  lea     r8, aSelectExistsSe_2; "SELECT EXISTS(SELECT 1 FROM Application"...
0x18001e480  mov     [rsp+40h+var_20], rax; int
0x18001e485  lea     rdx, aSelectExistsSe_1; "SELECT EXISTS(SELECT 1 FROM Application"...
0x18001e48c  mov     byte ptr [rbp+arg_18], 0
0x18001e490  mov     rcx, rsi; this
0x18001e493  call    ?PrepareAndBindAndExists@StatementExecution@StateRepository@@YAJAEAVDatabase@2@PEBD1_JAEA_N@Z; StateRepository::StatementExecution::PrepareAndBindAndExists(StateRepository::Database &,char const *,char const *,__int64,bool &)
0x18001e498  mov     rcx, [rbp+18h]; this
0x18001e49c  mov     ebx, eax
0x18001e49e  lea     r8, aOnecoreBaseApp_30; "onecore\\base\\appmodel\\staterepositor"...
0x18001e4a5  test    eax, eax
0x18001e4a7  jns     short loc_18001E4C3
0x18001e4a9  mov     r9d, eax; char *
0x18001e4ac  mov     edx, 23Ah; void *
0x18001e4b1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001e4b6  mov     r9d, ebx
0x18001e4b9  mov     edx, 4ACh
0x18001e4be  jmp     loc_18001E132
0x18001e4c3  cmp     byte ptr [rbp+arg_18], 0
0x18001e4c7  jz      short loc_18001E4DB
0x18001e4c9  mov     ebx, 80670001h
0x18001e4ce  mov     edx, 4ADh
0x18001e4d3  mov     r9d, ebx
0x18001e4d6  jmp     loc_18001E13D
0x18001e4db  mov     ebx, 80070490h
0x18001e4e0  mov     edx, 4AEh
0x18001e4e5  mov     r9d, ebx
0x18001e4e8  jmp     loc_18001E13D
0x18001e4ed  inc     qword ptr [rdi+8]
0x18001e4f1  xor     ebx, ebx
0x18001e4f3  mov     [rdi+10h], r14
0x18001e4f7  lea     rcx, [rbp+var_10]; this
0x18001e4fb  call    ??1Statement@StateRepository@@QEAA@XZ; StateRepository::Statement::~Statement(void)
0x18001e500  mov     rsi, [rsp+40h+arg_8]
0x18001e505  mov     eax, ebx
0x18001e507  mov     rbx, [rsp+40h+arg_0]
0x18001e50c  add     rsp, 40h
0x18001e510  pop     r14
0x18001e512  pop     rdi
0x18001e513  pop     rbp
0x18001e514  retn
```
