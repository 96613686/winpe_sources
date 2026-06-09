# FileToDir

- ea: `0x18000a750`
- end: `0x18000a8a6`
- name: `FileToDir`
- size: `342`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `2`
- callee_count: `6`
- tags: ``

## callers

- `0x18000a920`
- `0x18000ae60`

## callees

- `0x180002498`
- `0x1800099f8`
- `0x180009ab4`
- `0x180009b10`
- `0x180009d8c`
- `0x18000a750`

## import_xrefs

- `msvcrt!strchr` at `0x18000a7bf`
- `msvcrt!strchr` at `0x18000a7bf`
- `msvcrt!free` at `0x18000a872`
- `msvcrt!free` at `0x18000a872`
- `msvcrt!strrchr` at `0x18000a792`
- `msvcrt!strrchr` at `0x18000a792`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
String *__fastcall FileToDir(String *a1, __int64 *a2)
{
  __int64 v4; // rbx
  const char *v5; // rcx
  char *v6; // rax
  unsigned __int64 v7; // rdi
  __int64 v8; // rbx
  const char *v9; // rcx
  char *v10; // rax
  char *v11; // rax
  char *v12; // rbx
  char *v13; // r14
  unsigned __int64 v14; // rsi
  char *v15; // rax
  unsigned __int64 v16; // rax
  char *v17; // rcx
  char v18; // dl
  __int64 v20[6]; // [rsp+28h] [rbp-30h] BYREF

  String::String(a1, (bool)a2);
  v4 = *a2;
  v5 = *(const char **)(*a2 + 32);
  if ( v5 && (v6 = strrchr(v5, 92)) != 0 && (v7 = (unsigned __int64)&v6[-*(_QWORD *)(v4 + 32)], v7 != -1)
    || (v8 = *a2, (v9 = *(const char **)(*a2 + 32)) != 0)
    && (v10 = strchr(v9, 58)) != 0
    && (v11 = &v10[-*(_QWORD *)(v8 + 32)], v11 != (char *)-1LL)
    && (v7 = (unsigned __int64)(v11 + 1), v11 != (char *)-2LL) )
  {
    v12 = 0;
    v13 = *(char **)(*a2 + 32);
    if ( v13 )
    {
      v14 = v7 + 1;
      if ( v7 + 1 >= v7 )
      {
        v15 = (char *)operator new(v7 + 1);
        v12 = v15;
        if ( v15 )
        {
          if ( v7 != -1 )
          {
            if ( v14 <= 0x7FFFFFFF && v7 <= 0x7FFFFFFE )
            {
              v16 = v7;
              v17 = v12;
              do
              {
                if ( !v16 )
                  break;
                v18 = *v13;
                if ( !*v13 )
                  break;
                ++v13;
                *v17++ = v18;
                --v16;
                --v14;
              }
              while ( v14 );
              v15 = v17 - 1;
              if ( v14 )
                v15 = v17;
            }
            *v15 = 0;
          }
          v12[v7] = 0;
        }
      }
    }
    String::String((String *)v20, v12);
    if ( v12 )
      free(v12);
    TRefPtr<StringBuffer>::Set(a1, v20[0]);
    TRefPtr<CMonitorNotify>::~TRefPtr<CMonitorNotify>(v20);
  }
  return a1;
}

```

## disassembly

```asm
0x18000a750  mov     rax, rsp
0x18000a753  mov     [rax+10h], rbx
0x18000a757  mov     [rax+18h], rbp
0x18000a75b  mov     [rax+8], rcx
0x18000a75f  push    rsi
0x18000a760  push    rdi
0x18000a761  push    r14
0x18000a763  sub     rsp, 40h
0x18000a767  mov     rsi, rdx
0x18000a76a  mov     rbp, rcx
0x18000a76d  mov     dword ptr [rax-38h], 0
0x18000a774  call    ??0String@@QEAA@_N@Z; String::String(bool)
0x18000a779  mov     [rsp+58h+var_38], 1
0x18000a781  mov     rbx, [rsi]
0x18000a784  mov     rcx, [rbx+20h]; Str
0x18000a788  test    rcx, rcx
0x18000a78b  jz      short loc_18000A7AA
0x18000a78d  mov     edx, 5Ch ; '\'; Ch
0x18000a792  call    cs:__imp_strrchr
0x18000a798  mov     rdi, rax
0x18000a79b  test    rax, rax
0x18000a79e  jz      short loc_18000A7AA
0x18000a7a0  sub     rdi, [rbx+20h]
0x18000a7a4  cmp     rdi, 0FFFFFFFFFFFFFFFFh
0x18000a7a8  jnz     short loc_18000A7EA
0x18000a7aa  mov     rbx, [rsi]
0x18000a7ad  mov     rcx, [rbx+20h]; Str
0x18000a7b1  test    rcx, rcx
0x18000a7b4  jz      loc_18000A88F
0x18000a7ba  mov     edx, 3Ah ; ':'; Val
0x18000a7bf  call    cs:__imp_strchr
0x18000a7c5  test    rax, rax
0x18000a7c8  jz      loc_18000A88F
0x18000a7ce  sub     rax, [rbx+20h]
0x18000a7d2  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18000a7d6  jz      loc_18000A88F
0x18000a7dc  lea     rdi, [rax+1]
0x18000a7e0  cmp     rdi, 0FFFFFFFFFFFFFFFFh
0x18000a7e4  jz      loc_18000A88F
0x18000a7ea  xor     ebx, ebx
0x18000a7ec  mov     rax, [rsi]
0x18000a7ef  mov     r14, [rax+20h]
0x18000a7f3  test    r14, r14
0x18000a7f6  jz      short loc_18000A85D
0x18000a7f8  lea     rsi, [rdi+1]
0x18000a7fc  cmp     rsi, rdi
0x18000a7ff  jb      short loc_18000A85D
0x18000a801  mov     rcx, rsi; unsigned __int64
0x18000a804  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000a809  mov     rbx, rax
0x18000a80c  test    rax, rax
0x18000a80f  jz      short loc_18000A85D
0x18000a811  test    rsi, rsi
0x18000a814  jz      short loc_18000A859
0x18000a816  cmp     rsi, 7FFFFFFFh
0x18000a81d  ja      short loc_18000A856
0x18000a81f  cmp     rdi, 7FFFFFFEh
0x18000a826  ja      short loc_18000A856
0x18000a828  mov     rax, rdi
0x18000a82b  mov     rcx, rbx
0x18000a82e  test    rax, rax
0x18000a831  jz      short loc_18000A84B
0x18000a833  mov     dl, [r14]
0x18000a836  test    dl, dl
0x18000a838  jz      short loc_18000A84B
0x18000a83a  inc     r14
0x18000a83d  mov     [rcx], dl
0x18000a83f  inc     rcx
0x18000a842  dec     rax
0x18000a845  sub     rsi, 1
0x18000a849  jnz     short loc_18000A82E
0x18000a84b  lea     rax, [rcx-1]
0x18000a84f  test    rsi, rsi
0x18000a852  cmovnz  rax, rcx
0x18000a856  mov     byte ptr [rax], 0
0x18000a859  mov     byte ptr [rbx+rdi], 0
0x18000a85d  mov     rdx, rbx; char *
0x18000a860  lea     rcx, [rsp+58h+var_30]; this
0x18000a865  call    ??0String@@QEAA@PEBD_N@Z; String::String(char const *,bool)
0x18000a86a  test    rbx, rbx
0x18000a86d  jz      short loc_18000A878
0x18000a86f  mov     rcx, rbx; Block
0x18000a872  call    cs:__imp_free
0x18000a878  mov     rdx, [rsp+58h+var_30]
0x18000a87d  mov     rcx, rbp
0x18000a880  call    ?Set@?$TRefPtr@VStringBuffer@@@@QEAAXPEAVStringBuffer@@@Z; TRefPtr<StringBuffer>::Set(StringBuffer *)
0x18000a885  lea     rcx, [rsp+58h+var_30]
0x18000a88a  call    ??1?$TRefPtr@VCMonitorNotify@@@@QEAA@XZ; TRefPtr<CMonitorNotify>::~TRefPtr<CMonitorNotify>(void)
0x18000a88f  mov     rax, rbp
0x18000a892  mov     rbx, [rsp+58h+arg_8]
0x18000a897  mov     rbp, [rsp+58h+arg_10]
0x18000a89c  add     rsp, 40h
0x18000a8a0  pop     r14
0x18000a8a2  pop     rdi
0x18000a8a3  pop     rsi
0x18000a8a4  retn
```
