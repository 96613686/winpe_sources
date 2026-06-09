# CDriveConfiguration::CDriveConfiguration(CDriveConfiguration const &)

- ea: `0x180001d70`
- end: `0x180001eb9`
- name: `??0CDriveConfiguration@@QEAA@AEBV0@@Z`
- size: `329`
- prototype: `CDriveConfiguration *__fastcall(CDriveConfiguration *__hidden this, const struct CDriveConfiguration *)`
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config`

## callees

- `0x180001d70`

## pseudocode

```c
CDriveConfiguration *__fastcall CDriveConfiguration::CDriveConfiguration(
        CDriveConfiguration *this,
        const struct CDriveConfiguration *a2)
{
  __int64 v2; // r9
  _OWORD *v4; // rax
  _OWORD *v5; // rcx
  __int128 v6; // xmm1

  v2 = 8;
  *(_BYTE *)this = *(_BYTE *)a2;
  *((_DWORD *)this + 1) = *((_DWORD *)a2 + 1);
  *((_DWORD *)this + 2) = *((_DWORD *)a2 + 2);
  *((_BYTE *)this + 12) = *((_BYTE *)a2 + 12);
  *((_DWORD *)this + 4) = *((_DWORD *)a2 + 4);
  v4 = (_OWORD *)((char *)a2 + 64);
  *(_OWORD *)((char *)this + 24) = *(_OWORD *)((char *)a2 + 24);
  *(_OWORD *)((char *)this + 40) = *(_OWORD *)((char *)a2 + 40);
  *((_QWORD *)this + 7) = *((_QWORD *)a2 + 7);
  v5 = (_OWORD *)((char *)this + 64);
  do
  {
    *v5 = *v4;
    v5[1] = v4[1];
    v5[2] = v4[2];
    v5[3] = v4[3];
    v5[4] = v4[4];
    v5[5] = v4[5];
    v5[6] = v4[6];
    v6 = v4[7];
    v4 += 8;
    v5[7] = v6;
    v5 += 8;
    --v2;
  }
  while ( v2 );
  *v5 = *v4;
  v5[1] = v4[1];
  v5[2] = v4[2];
  v5[3] = v4[3];
  v5[4] = v4[4];
  *((_QWORD *)v5 + 10) = *((_QWORD *)v4 + 10);
  *(_OWORD *)((char *)this + 1176) = *(_OWORD *)((char *)a2 + 1176);
  *(_OWORD *)((char *)this + 1192) = *(_OWORD *)((char *)a2 + 1192);
  *(_OWORD *)((char *)this + 1208) = *(_OWORD *)((char *)a2 + 1208);
  *(_OWORD *)((char *)this + 1224) = *(_OWORD *)((char *)a2 + 1224);
  *(_OWORD *)((char *)this + 1240) = *(_OWORD *)((char *)a2 + 1240);
  *((_QWORD *)this + 157) = *((_QWORD *)a2 + 157);
  *((_DWORD *)this + 316) = *((_DWORD *)a2 + 316);
  *((_QWORD *)this + 159) = *((_QWORD *)a2 + 159);
  *((_QWORD *)this + 160) = *((_QWORD *)a2 + 160);
  return this;
}

```

## disassembly

```asm
0x180001d70  mov     al, [rdx]; public: CDriveConfiguration::CDriveConfiguration(class CDriveConfiguration const &)
0x180001d72  mov     r9d, 8
0x180001d78  mov     [rcx], al
0x180001d7a  mov     r8, rcx
0x180001d7d  mov     eax, [rdx+4]
0x180001d80  mov     [rcx+4], eax
0x180001d83  mov     eax, [rdx+8]
0x180001d86  lea     r10d, [r9+78h]
0x180001d8a  mov     [rcx+8], eax
0x180001d8d  mov     al, [rdx+0Ch]
0x180001d90  mov     [rcx+0Ch], al
0x180001d93  mov     eax, [rdx+10h]
0x180001d96  mov     [rcx+10h], eax
0x180001d99  lea     rax, [rdx+40h]
0x180001d9d  movups  xmm0, xmmword ptr [rdx+18h]
0x180001da1  movups  xmmword ptr [rcx+18h], xmm0
0x180001da5  movups  xmm1, xmmword ptr [rdx+28h]
0x180001da9  movups  xmmword ptr [rcx+28h], xmm1
0x180001dad  movsd   xmm0, qword ptr [rdx+38h]
0x180001db2  movsd   qword ptr [rcx+38h], xmm0
0x180001db7  add     rcx, 40h ; '@'
0x180001dbb  movups  xmm0, xmmword ptr [rax]
0x180001dbe  movups  xmmword ptr [rcx], xmm0
0x180001dc1  movups  xmm1, xmmword ptr [rax+10h]
0x180001dc5  movups  xmmword ptr [rcx+10h], xmm1
0x180001dc9  movups  xmm0, xmmword ptr [rax+20h]
0x180001dcd  movups  xmmword ptr [rcx+20h], xmm0
0x180001dd1  movups  xmm1, xmmword ptr [rax+30h]
0x180001dd5  movups  xmmword ptr [rcx+30h], xmm1
0x180001dd9  movups  xmm0, xmmword ptr [rax+40h]
0x180001ddd  movups  xmmword ptr [rcx+40h], xmm0
0x180001de1  movups  xmm1, xmmword ptr [rax+50h]
0x180001de5  movups  xmmword ptr [rcx+50h], xmm1
0x180001de9  movups  xmm0, xmmword ptr [rax+60h]
0x180001ded  movups  xmmword ptr [rcx+60h], xmm0
0x180001df1  movups  xmm1, xmmword ptr [rax+70h]
0x180001df5  add     rax, r10
0x180001df8  movups  xmmword ptr [rcx+70h], xmm1
0x180001dfc  add     rcx, r10
0x180001dff  sub     r9, 1
0x180001e03  jnz     short loc_180001DBB
0x180001e05  movups  xmm0, xmmword ptr [rax]
0x180001e08  movups  xmmword ptr [rcx], xmm0
0x180001e0b  movups  xmm1, xmmword ptr [rax+10h]
0x180001e0f  movups  xmmword ptr [rcx+10h], xmm1
0x180001e13  movups  xmm0, xmmword ptr [rax+20h]
0x180001e17  movups  xmmword ptr [rcx+20h], xmm0
0x180001e1b  movups  xmm1, xmmword ptr [rax+30h]
0x180001e1f  movups  xmmword ptr [rcx+30h], xmm1
0x180001e23  movups  xmm0, xmmword ptr [rax+40h]
0x180001e27  movups  xmmword ptr [rcx+40h], xmm0
0x180001e2b  mov     rax, [rax+50h]
0x180001e2f  mov     [rcx+50h], rax
0x180001e33  movups  xmm0, xmmword ptr [rdx+498h]
0x180001e3a  movups  xmmword ptr [r8+498h], xmm0
0x180001e42  movups  xmm1, xmmword ptr [rdx+4A8h]
0x180001e49  movups  xmmword ptr [r8+4A8h], xmm1
0x180001e51  movups  xmm0, xmmword ptr [rdx+4B8h]
0x180001e58  movups  xmmword ptr [r8+4B8h], xmm0
0x180001e60  movups  xmm1, xmmword ptr [rdx+4C8h]
0x180001e67  movups  xmmword ptr [r8+4C8h], xmm1
0x180001e6f  movups  xmm0, xmmword ptr [rdx+4D8h]
0x180001e76  movups  xmmword ptr [r8+4D8h], xmm0
0x180001e7e  mov     rax, [rdx+4E8h]
0x180001e85  mov     [r8+4E8h], rax
0x180001e8c  mov     eax, [rdx+4F0h]
0x180001e92  mov     [r8+4F0h], eax
0x180001e99  mov     rax, [rdx+4F8h]
0x180001ea0  mov     [r8+4F8h], rax
0x180001ea7  mov     rax, [rdx+500h]
0x180001eae  mov     [r8+500h], rax
0x180001eb5  mov     rax, r8
0x180001eb8  retn
```
